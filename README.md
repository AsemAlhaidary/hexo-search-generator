# hexo-search-generator

This is an updated version of the [hexo-generator-search](https://github.com/wzpan/hexo-generator-search) package

The output file (search.xml) of the original package was missing to some informations about the posts, so I have made this updated version to add the informations that I need in my projects

## Install

``` bash
$ npm install hexo-search-generator --save
```

## Options

You can configure this plugin in your root `_config.yml`.

``` yaml
search:
  path: search.xml
  field: post
  content: true
  template: ./search.xml
```

- **path** - file path. By default is `search.xml` . If the file extension is `.json`, the output format will be JSON. Otherwise XML format file will be exported.
- **field** - the search scope you want to search, you can chose:
  * **post** (Default) - will only covers all the posts of your blog.
  * **page** - will only covers all the pages of your blog.
  * **all** - will covers all the posts and pages of your blog.
- **content** - whether contains the whole content of each article. If `false`, the generated results only cover title and other meta info without mainbody. By default is `true`.
- **template** (Optional) - path to a custom XML template

## Exclude indexing

To exclude a certain post or page from being indexed, you can simply insert `indexing: false` setting at the top of its front-matter, *e.g.*:

```
title: "Code Highlight"
date: "2014-03-15 20:17:16"
tags: highlight
categories: Demo
description: "A collection of Hello World applications from helloworld.org."
toc: true
indexing: false
---
```

Then the generated result will not contain this post or page.

## Output

The output will be like
```xml
<entry>
  <title>Your Online Data Is in Peril &amp; the Blockchain Could Save It</title>
  <link href="/Science_科学/Technology_技術/Your-Online-Data-Is-In-Peril-the-Blockchain-Could-Save-It/"/>
  <url>/Science_%E7%A7%91%E5%AD%A6/Technology_%E6%8A%80%E8%A1%93/Your-Online-Data-Is-In-Peril-the-Blockchain-Could-Save-It/</url>
  <published>Thu Mar 31 2022 06:02:35 GMT+0300</published>
  <modified>Thu Mar 31 2022 06:02:35 GMT+0300</modified>
  <content type="html"><![CDATA[Lorem, ipsum dolor sit amet consectetur adipisicing elit.]]></content>
  <categories>
    <category>Science_科学</category>
    <category>Technology_技術</category>
  </categories>
  <tags>
    <tag>Blockchain</tag>
    <tag>Security</tag>
  </tags>
</entry>
```

## FAQ

### What's this plugin supposed to do? 

This plugin is used for generating a xml / json file from your Hexo blog that provides data for searching.

### Where's this file saved to?

After executing `hexo g` you will get the generated result at your public folder.

## Sponsor
I have created and used this package in my sponsor's [Blog](https://blog.richiebartlett.com/), you can find him at his [Website](https://richiebartlett.com/), also [Github](https://github.com/lorezyra)