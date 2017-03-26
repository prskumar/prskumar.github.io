---
layout: page
title: "Cheatsheet"
comments: true
sharing: true
footer: true
---

* list element with functor item
{:toc}

* Steps to regenerate and publish to github
	* `rake preview` - regenerates HTML files from .md files. To preview locally visit: http:localhost:4000
	* `rake deploy` - deploy the new HTML changes to the remote github
	* Enter below commands to add the md files to Github

```
git add .
git commit -m 'commit message'
git push origin source
```

