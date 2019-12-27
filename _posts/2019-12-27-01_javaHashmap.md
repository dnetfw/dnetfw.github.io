---
title: "java HashMap"
excerpt: "java 해시맵 사용법"
date: 2019-12-27 09:08
categories: "java"
tag: ["javascript", "HashMap"]
lastmod : 2019-12-27 09:08
published : true
sitemap :
  changefreq : daily
  priority : 1.0
---


# Java Hashmap

해시맵이란 Map을 구현하며, Key Value 구조로 하나의 entry를 구성한다.

hashing 기술을 통하여 많은양의 데이터를 검색하는데도 뛰어나다.

특징
1. Map 인터페이스의 한 종류 ("Key", "value") 로 이루어짐
2. Key 값은 중복이 불가능. value 는 중복가능, value 에 null 사용 가능
3. 멀티쓰레드에서 HashMap은 문제가 발생할 수 있어서 멀티쓰레드 환경에서는 HashTable 을 주로 사용

```java
HashMap<String, String> hMap = new HashMap<>();

hMap.put("Name","dnetfw");
hMap.put("age", "26");

System.out.println(hMap); // {"Name" : "dnetfw" , "age" : "26"}

hMap.get("Name"); // "dnetfw"
hMap.get("age"); // "26"
Set set = hMap.entrySet();

Iterator iterator = set.iterator();

while(iterator.hasNext()){

  Map.Entry entry = (Map.Entry)iterator.next();

  String key = (String)entry.getKey();

  String value = (String)entry.getValue();

  System.out.println("hashMap Key : " + key); // "hashMap key : Name , age

  System.out.println("hashMap Value : " + value); // "hashMap value : dnetfw, 26

}

```