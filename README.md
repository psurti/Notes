Bookmarks on different topics:

#### [Microservices](https://github.com/psurti/Notes/blob/master/Microservices.md)
#### [Docker and Kubermetes](https://github.com/psurti/Notes/blob/master/Docker-Kubernetes.md)
```
 % docker-machine start linux
 % docker ps
 % docker images
 % docker run -it alpine sh
```
#### [Git and Gerrit](https://github.com/psurti/Notes/blob/master/Git-Gerrit.md)
```
1. Local committed changes

2. git pull -r origin master

 CASE you forgot -r(rebase) in previous command then do to resolve merge commit:
 > git rebase -i
 > git commit --amend (remove the pre-existing gerrit change Id or push will be rejected)

3. git push origin HEAD:refs/for/master
```
#### Jenkins
#### Gradle
###### Pass environment parameters to gradlew bootRun task
  1. Add to build.gradle
  ```gradle
  bootRun {
    systemProperties = System.properties
  }
  ```
  2. Run bootRun task
  ```gradle
  gradlew -Dspring.profiles.active=dev bootRun
  ```
  3. To add local dependency instead use
  ```gradle
      //compile 'com.xyz:foo-bar:2.+'
      compile fileTree(dir: 'c:/git/xyz/build/libs', include: '*.jar')
  ```
#### Lucene
#### [Elasticsearch](https://github.com/psurti/Notes/blob/master/ElasticSearch.md)
#### [Kafka and Pulsar](https://github.com/psurti/Notes/blob/master/Kafka-Pulsar.md)
#### Solr
#### [GoLang](https://github.com/psurti/Notes/blob/master/GoLang.md)
#### [Kotlin](https://github.com/psurti/Notes/blob/master/Kotlin.md)
#### Spring boot/framework
#### Java
#### Redis
#### Hazelcast
#### Python
#### Nodejs
#### React.js
#### Vue.js
#### JavaScript
#### [Domain Driven Design](https://github.com/psurti/Notes/blob/master/DDD.md)
#### [Security](https://github.com/psurti/Notes/blob/master/Security.md)
#### [Statistics](https://github.com/psurti/Notes/blob/master/Statistics.md)
#### [Spring](https://github.com/psurti/Notes/blob/master/Spring.md)
#### [MachineLearning](https://github.com/psurti/Notes/blob/master/ML.md)
