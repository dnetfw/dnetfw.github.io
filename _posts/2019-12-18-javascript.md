---
title: "javascript 날짜 차이"
excerpt: "vbscript to javascript"
date: 2019-12-18 07:59
categories: "Javascript"
tag: ["javascript" , "vbscript"]
lastmod : 2019-12-18 07:59
sitemap :
  changefreq : daily
  priority : 1.0
---


```javascript
function GF_013(Arg1, Arg2){ // dnetfw
		var diffDate_1 = Arg1 instanceof Date ? Arg1 : new Date(Arg1);
		var diffDate_2 = Arg2 instanceof Date ? Arg2 : new Date(Arg2);

		diffDate_1 =new Date(diffDate_1.getFullYear(), diffDate_1.getMonth()+1, diffDate_1.getDate());
		diffDate_2 =new Date(diffDate_2.getFullYear(), diffDate_2.getMonth()+1, diffDate_2.getDate());

		var diff = Math.abs(diffDate_2.getTime() - diffDate_1.getTime());
		diff = Math.ceil(diff / (1000 * 3600 * 24));

		return diff;

	}
```