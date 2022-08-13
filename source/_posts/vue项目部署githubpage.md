---
title: vue3部署githubpage
tags: [record, study]
date: 2021-06-11
categories: 
- github


index_img: /img/pexels-mohamed-sarim-1033729.jpg

---


```
npm run build
git checkout -b gh-pages
git add -f dist
git commit -m 'first commit'
git subtree push --prefix dist origin gh-pages


```
