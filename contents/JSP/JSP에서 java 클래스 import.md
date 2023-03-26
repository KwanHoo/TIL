# _JSP 에서 JAVA 클래스 import 하기_

### 사용법

- 불러올 JSP 페이지에서

```jsp
    <%@ page import="member.Member" %> // 이런식으로 하면된다. ->"패키지이름 . 클래스이름"
```

### 예시

- 자바

```java
package member;

public class Member
{
    String name;

    public Member(String name)
    {
        this.name=name;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

- JSP

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<%@ page import="member.Member" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>JSP04 예제</title>
</head>
<body>
<%
    Member m = new Member("염소");
%>

이름 :<font size=10><%=m.getName() %></font>
</body>
</html>
```

[참고포스팅](https://goat-park.tistory.com/3)
