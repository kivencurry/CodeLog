### t1:computeIfAbsent() 的使用:
不使用computeIfAbsent()
~~~ java
    // 判断map中是否存在，如果存在则添加元素到set中，如果不存在则新建set添加到hashMap中
    if(hashMap.containsKey("china")) {
      hashMap.get("china").add("liSi");
    } else {
      Set<String> setTmp = new HashSet<>();
      setTmp.add("liSi");
      hashMap.put("china", setTmp);
    }
  }
}
~~~
使用computeIfAbsent()
~~~java
    // after JDK1.8,use computerIfAbsent
    hashMap.computeIfAbsent("china", key -> getValues(key)).add("liSi");
    System.out.println(hashMap.toString());
  }
 
  public static HashSet getValues(String key) {
    return new HashSet();
  }
}
~~~
