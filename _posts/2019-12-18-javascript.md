---
title: "javascript 날짜 차이 및 오브젝트 형 파악"
excerpt: "vbscript to javascript"
date: 2019-12-18 07:59
categories: "Javascript"
tag: ["javascript" , "vbscript"]
lastmod : 2019-12-18 07:59
sitemap :
  changefreq : daily
  priority : 1.0
---

## 두 날짜간 몇일 차이인지 비교

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

## javascript IsObject

```javascript
	function object(str){ // dnetfw
		return str.constructor === Object;
	}
```

## P.S == 과 ===의 차이점

a == b  같은 경우엔 a와 b의 데이터 값을 비교한다.

a === b 같은 경우엔 a와 b의 데이터 값 및 타입/형식 까지 비교한다. (좀 더 정밀하게);