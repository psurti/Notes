https://howtodoinjava.com/java/collections/java-priorityqueue/  
https://www.codepedia.org/ama/how-to-make-parallel-calls-in-java-with-completablefuture-example  

#### printf format syntax
https://www.cs.colostate.edu/~cs160/.Summer16/resources/Java_printf_method_quick_reference.pdf   

#### Streams API
https://www.nurkiewicz.com/2014/07/grouping-sampling-and-batching-custom.html   
http://minborgsjavapot.blogspot.com/2019/10/become-master-of-java-streams-part-4.html   
https://www.optaplanner.org/blog/2018/01/09/JavaReflectionButMuchFaster.html   


#### Troubleshooting DirectMemory Buffers
https://dzone.com/articles/troubleshooting-problems-with-native-off-heap-memo   





```java
int BATCH = 500;
IntStream.range(0, (data.size()+BATCH-1)/BATCH)
         .mapToObj(i -> data.subList(i*BATCH, Math.min(data.size(), (i+1)*BATCH)))
         .forEach(batch -> process(batch))
```

#### Reverse Proxy to Java Backend Service
https://medium.com/@mirela95/apache-http-server-as-reverse-proxy-with-java-back-end-application-running-on-tomcat-9c8c9210783e  
