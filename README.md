[![Maven Central](https://img.shields.io/maven-central/v/com.ajaxjs/aj-json?label=Latest%20Release)](https://central.sonatype.com/artifact/com.ajaxjs/aj-json)
[![Javadoc](https://img.shields.io/badge/javadoc-1.4-brightgreen.svg?)](https://javadoc.io/doc/com.ajaxjs/aj-json)
[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/lightweight-component/aj-json)
[![License](https://img.shields.io/badge/license-Apache--2.0-green.svg?longCache=true&style=flat)](http://www.apache.org/licenses/LICENSE-2.0.txt)
[![Email](https://img.shields.io/badge/Contact--me-Email-orange.svg)](mailto:frank@ajaxjs.com)

# Small JSON parser & serializer 小型 JSON 解释器

小型 JSON 解析器，实现 JSON 与 Map/List 互换，是了解 JSON 解析的好例子。

This is a lightweight JSON parser that implements bidirectional conversion between JSON strings and Java data structures such as Map and List. 
The implementation is simple yet powerful, making it an excellent example for learning how JSON parsing works under the hood.

## Source code

[Github](https://github.com/lightweight-component/aj-json) | [Gitcode](https://gitcode.com/lightweight-component/aj-json)


# Install
Requires Java 1.8+, Maven Snippets:

```xml
<dependency>
    <groupId>com.ajaxjs</groupId>
    <artifactId>aj-json</artifactId>
    <version>1.4</version>
</dependency>
```

# Usage

```java
// Java to JSON
Object obj = true;
String json = ConvertToJson.toJson(obj);
assertEquals("true", json);

obj = 123;
json = ConvertToJson.toJson(obj);
assertEquals("123", json);

obj = 100000000000000001L;
json = ConvertToJson.toJson(obj);
assertEquals("\"100000000000000001\"", json);

obj = 99999L;
json = ConvertToJson.toJson(obj);
assertEquals("99999", json);

obj = "hello";
json = ConvertToJson.toJson(obj);
assertEquals("\"hello\"", json);

Map map = new HashMap();
map.put("name", "John");
map.put("age", 30);
json = ConvertToJson.toJson(map);
assertEquals("{\"name\":\"John\",\"age\":30}", json);   

// List to JSON
List list = new ArrayList();
list.add(1);
list.add(2);
list.add(3);
String json = ConvertToJson.list2Json(list);
assertEquals("[1, 2, 3]", json);
```