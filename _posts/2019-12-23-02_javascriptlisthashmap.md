---
title: "javascript List 및 hashmap 구현"
excerpt: "javascript List, hashmap"
date: 2019-12-23 22:13
categories: "javascript"
tag: ["javascript"]
lastmod : 2019-12-23 22:13
published : true
sitemap :
  changefreq : daily
  priority : 1.0
---

# LIST

```javascript

function List(){
	this.elements = {};
	this.idx = 0;
	this.length = 0;
}

List.prototype.add = function(element){
	this.length++;
	this.elements[this.idx++] = element;
}

List.prototype.get = function(idx){
	return this.elements[idx];
}
```

사용방법은
```javascript
var list = new List();

list.add('test'); // 순서대로 넣기

list.get(0); // 가져오기
```


# HASHMAP
```javascript
var hMap = function(){
    this.map = new Object();
}
 
hMap.prototype = {
    put: function (key, value) {
        this.map[key] = value;
    },
    get: function (key) {
        return this.map[key];
    },
    containsKey: function (key) {
        return key in this.map;
    },
    containsValue: function (value) {
        for (var prop in this.map) {
            if (this.map[prop] == value) {
                return true;
            }
        }
        return false;
    },
    clear: function () {
        for (var prop in this.map) {
            delete this.map[prop];
        }
    },
    remove: function (key) {
        delete this.map[key];
    },
    keys: function () {
        var arKey = new Array();
        for (var prop in this.map) {
            arKey.push(prop);
        }
        return arKey;
    },
    values: function () {
        var arVal = new Array();
        for (var prop in this.map) {
            arVal.push(this.map[prop]);
        }
        return arVal;
    },
    size: function () {
        var count = 0;
        for (var prop in this.map) {
            count++;
        }
        return count;
    }
}
```