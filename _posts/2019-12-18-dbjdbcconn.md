---
title: "JAVA DB 연결"
excerpt: "db 연동"
date: 2019-12-18 16:52
categories: "java"
tag: ["java" , "jsp", "mssql"]
lastmod : 2019-12-18 16:53
sitemap :
  changefreq : daily
  priority : 1.0
---


## jsp에서 DB연결 하는 생성자 부분

```java
public 생성자() {
    // 새로운 jdbc 업로드 7.4.1.0 버전 (이전버전 jdbc42) - 191217 15:07
    String connectionUrl = "jdbc:sqlserver://dbip명:dbport;databaseName=db명;user=계정명;password=패스워드";
    try {
        con = DriverManager.getConnection(connectionUrl);
    }catch(SQLException e) {
        e.printStackTrace();
    }
    try (Statement stmt = con.createStatement();){
        System.out.println("연결 성공");
    } catch(SQLException e) {
        e.printStackTrace();
    }
}
```

## 프로젝트 일부 발췌 jsp List 사용법

```java
public List getLog() {
    String SQL = "select top 1 * from db명 order by no desc;";
    
    try {
        //System.out.println(userID);
        //System.out.println(userPassword);
        pstmt = con.prepareStatement(SQL);
        //pstmt.setString(1,  "no");
        rs = pstmt.executeQuery();
        if(rs.next()) {
            List list = new ArrayList();
            list.add(rs.getString("NO"));
            list.add(rs.getString("Code"));
            list.add(rs.getString("Message"));
            list.add(rs.getString("Time"));
            list.add(rs.getString("Grade"));
            list.add(rs.getString("Device"));
            list.add(rs.getString("Building"));
            return list;
        }
        //return -1; // 아디 없즘
        
    }catch(Exception e) {
        e.printStackTrace();
    }
    List list = new ArrayList();
    list.add("error");
    return list; // 디비 연결도안됨
}
```