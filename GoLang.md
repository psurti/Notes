##### Tutorials
https://objectcomputing.com/resources/publications/sett/november-2018-way-to-go-part-1 
https://objectcomputing.com/resources/publications/go-for-it-part-2 
https://objectcomputing.com/resources/publications/sett/april-2019-way-to-go-part-3  
https://medium.com/free-code-camp/learning-go-from-zero-to-hero-d2a3223b3d86  
https://quii.gitbook.io/learn-go-with-tests/   
https://gobyexample.com/   
http://www.golangbootcamp.com/book   
https://golangdocs.com   
https://www.golangprograms.com/go-language   
https://tutorialedge.net/golang/writing-a-twitter-bot-golang/   
https://www.integralist.co.uk/posts/go-interfaces/   



##### Call C from Go
https://karthikkaranth.me/blog/calling-c-code-from-go/

##### Functional Interfaces in Go
https://karthikkaranth.me/blog/functions-implementing-interfaces-in-go/

##### Go cookbooks
https://blog.kowalczyk.info/book/go-cookbook.html    
https://golangdocs.com/   
https://www.alexedwards.net/blog/an-overview-of-go-tooling    
https://quii.gitbook.io/learn-go-with-tests/   

##### Call Go shared from Java
https://stackoverflow.com/questions/49986729/how-to-call-go-function-from-java-using-java-native-interface   
https://blog.dogan.io/2015/08/15/java-jni-jnr-go/   

##### Go and V8 (Javascript)
https://bravenewmethod.com/2011/03/30/embedding-v8-javascript-engine-and-go/   

##### Deserializing JSON in GO
https://medium.com/@fsufitch/deserializing-json-in-go-a-tutorial-d042412958ea    
https://jhall.io/posts/go-json-tricks-slightly-custom-marshaler/   


##### Design Patterns in GO
https://refactoring.guru/   
https://threedots.tech/   


##### Go micro-services framework
https://micro.mu/getting-started

##### Go Rest client
https://medium.com/@marcus.olsson/writing-a-go-client-for-your-restful-api-c193a2f4998c


#### Go lang - enums
https://yourbasic.org/golang/iota/    

#### Go lang - slice to slice-pointers
https://stackoverflow.com/questions/48459846/convert-slice-of-string-to-slice-of-pointer-to-string   


#### Good Go Makefile
https://kodfabrik.com/journal/a-good-makefile-for-go

#### Go lang /sqlite /mingw-64

https://medium.com/@yaravind/go-sqlite-on-windows-f91ef2dacfe   
https://jmeubank.github.io/tdm-gcc/

#### Go lang - JSON marshall/unmarshall null values
https://www.calhoun.io/how-to-determine-if-a-json-key-has-been-set-to-null-or-not-provided/   
https://www.sohamkamani.com/golang/omitempty/  
https://stackoverflow.com/questions/59964619/difference-using-pointer-in-struct-fields   
https://willnorris.com/2014/05/go-rest-apis-and-pointers/   


#### Gorm
https://medium.com/@sonus21/gorm-association-t-1-to-1-database-query-9415481300c    
https://blog.depa.do/post/gorm-gotchas   
https://medium.com/@luismasuelli/lets-order-a-pizza-in-go-part-1-4d70cbabb4ae   (4-part series)
https://stackoverflow.com/questions/63256680/adding-an-array-of-integers-as-a-data-type-in-a-gorm-model   (psql arrays)
https://github.com/go-gorm/gorm/issues/3585  (root->branch-leaf example)   
https://github.com/go-gorm/gorm/issues/3450  (custom join table)   
https://stackoverflow.com/questions/65012939/custom-fields-in-many2many-jointable  (custom join table)

#### Data structures
https://golang.org/doc/play/tree.go   
https://gist.github.com/fearblackcat/02970015071e63487d964f28f78d938c   
https://medium.com/analytics-vidhya/how-to-speed-up-a-tree-structure-traversal-in-go-cd4bd6775520   
https://ieftimov.com/post/golang-datastructures-trees/   


#### Go Channels
https://johncodes.com/posts/golang-performance/   


# How to update the Go version

System: Debian/Ubuntu/Fedora. Might work for others as well.

### 1. Uninstall the exisiting version

As mentioned [here](https://golang.org/doc/install#install), to update a go version you will first need to uninstall the original version.

To uninstall, delete the `/usr/local/go` directory by:

```
$ sudo rm -rf /usr/local/go
```

### 2. Install the new version

Go to the [downloads](https://golang.org/dl/) page and download the binary release suitable for your system.

### 3. Extract the archive file

To extract the archive file:

```
$ sudo tar -C /usr/local -xzf /home/nikhita/Downloads/go1.8.1.linux-amd64.tar.gz
```

### 4. Make sure that your PATH contains `/usr/local/go/bin`

```
$ echo $PATH | grep "/usr/local/go/bin"
```
