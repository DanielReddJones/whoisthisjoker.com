---
title: "RSS Feed now fixed!"
date: 2023-09-04
draft: false
tags: [
  "blog", "rss", "xml"]
categories: [
  "customization"]
---


The RSS feed now shows the full body of every article, as of today! 
For some reason, Hugo chooses by default to only include the description of an article in 
the RSS feed rather than put everything into the feed. 
This, obviously, defeats the purpose of having RSS to begin with. 

To fix this, I had to create rss.xml under themes>installed theme(hugo.386 for this site)>_default. 
I then posted the following xml into it. rss.xml overrides the default rss feed with custom settings, 
so that if there is something you want to include/exclude, you can do so.

Now, I cannot take credit for this XML as much as I want to. Huge thanks to [godo.dev](https://www.godo.dev/tutorials/hugo-full-text-rss/)[[mirror](https://web.archive.org/web/20230401070022/https://www.godo.dev/tutorials/hugo-full-text-rss/)] for providing an excellent tutorial on how to do this! 


```xml
<rss version="2.0" xmlns:atom="http://www.w3.org/2005/Atom">
  <channel>
    <title>{{ if eq  .Title  .Site.Title }}{{ .Site.Title }}{{ else }}{{ with .Title }}{{.}} on {{ end }}{{ .Site.Title }}{{ end }}</title>
    <link>{{ .Permalink }}</link>
    <description>Recent content {{ if ne  .Title  .Site.Title }}{{ with .Title }}in {{.}} {{ end }}{{ end }}on {{ .Site.Title }}</description>
    <generator>Hugo -- gohugo.io</generator>{{ with .Site.LanguageCode }}
    <language>{{.}}</language>{{end}}{{ with .Site.Author.email }}
    <managingEditor>{{.}}{{ with $.Site.Author.name }} ({{.}}){{end}}</managingEditor>{{end}}{{ with .Site.Author.email }}
    <webMaster>{{.}}{{ with $.Site.Author.name }} ({{.}}){{end}}</webMaster>{{end}}{{ with .Site.Copyright }}
    <copyright>{{.}}</copyright>{{end}}{{ if not .Date.IsZero }}
    <lastBuildDate>{{ .Date.Format "Mon, 02 Jan 2006 15:04:05 -0700" | safeHTML }}</lastBuildDate>{{ end }}
    {{ with .OutputFormats.Get "RSS" }}
        {{ printf "<atom:link href=%q rel=\"self\" type=%q />" .Permalink .MediaType | safeHTML }}
    {{ end }}
    {{ range .Pages }}
    <item>
      <title>{{ .Title }}</title>
      <link>{{ .Permalink }}</link>
      <pubDate>{{ .Date.Format "Mon, 02 Jan 2006 15:04:05 -0700" | safeHTML }}</pubDate>
      {{ with .Site.Author.email }}<author>{{.}}{{ with $.Site.Author.name }} ({{.}}){{end}}</author>{{end}}
      <guid>{{ .Permalink }}</guid>
      <description>{{- .Content | html -}}</description>
    </item>
    {{ end }}
  </channel>
</rss>
```

