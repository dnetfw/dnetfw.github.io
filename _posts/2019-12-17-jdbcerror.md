---
title: "MSSQL JAVA no suitable driver found for jdbc 에러"
excerpt: "연결 문제 해결 방법"
date: 2019-12-17 15:25
categories: "JAVA"
tag: ["JDBC", "JAVA", "MSSQL"]
lastmod : 2019-12-17 15:25
sitemap :
  changefreq : daily
  priority : 1.0
---

# 문제사항
## 1. java.sql.SQLException: No suitable driver found for jdbc:microsoft:sqlserver://...

해당 에러가 발생했을때 해결하지 못하여 고민을 많이했다.

이것저것 MSDN 문서도 찾아보며 다녔고,

![이미지 1](../assets/images/jdbcrequire.png)

시스템 요구사항도 확인 하였으며, 문제가 없다는 것을 확인했다.

다운로드 링크 : [Microsoft JDBC Driver 7.4 for SQL Server](https://www.microsoft.com/ko-KR/download/details.aspx?id=58505)

해당 파일에서 여러 샘플 데이터들을 다운로드 받을 수 있었다.

그중 눈에 띈 부분은, 샘플 ConnectURL.java 부분이였다.

```{.java}
public static void main(String[] args) {

        // Create a variable for the connection string.
        String connectionUrl = "jdbc:sqlserver://<server>:<port>;databaseName=AdventureWorks;user=<user>;password=<password>";

        try (Connection con = DriverManager.getConnection(connectionUrl); Statement stmt = con.createStatement();) {
            String SQL = "SELECT TOP 10 * FROM Person.Contact";
            ResultSet rs = stmt.executeQuery(SQL);

            // Iterate through the data in the result set and display it.
            while (rs.next()) {
                System.out.println(rs.getString("FirstName") + " " + rs.getString("LastName"));
            }
        }
        // Handle any errors that may have occurred.
        catch (SQLException e) {
            e.printStackTrace();
        }
    }
```