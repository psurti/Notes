![alt text](https://edwardthienhoang.files.wordpress.com/2017/12/100-explicit-architecture-svg.png "HexArch")

https://cargo-tracker.gitbook.io/documentation/  
https://github.com/citerus/dddsample-core  
https://www.mirkosertic.de/blog/2013/04/domain-driven-design-example/  
https://buildplease.com/pages/  
https://fideloper.com/hexagonal-architecture   


#### Hexagonal Architecture and DDD
https://www.freecodecamp.org/news/implementing-a-hexagonal-architecture/      
https://stakeholderwhisperer.com/posts/2014/10/introducing-modelling-by-example#_=_   
https://medium.com/swlh/implementing-a-hexagonal-architecture-bcfbe0d63622   
https://paulovich.net/rich-domain-model-with-ddd-tdd-reviewed/   
https://softwarecampament.wordpress.com/portsadapters/   
https://blog.octo.com/en/hexagonal-architecture-three-principles-and-an-implementation-example/   
https://vaadin.com/learn/tutorials/ddd   
https://beyondxscratch.com/2017/08/19/hexagonal-architecture-the-practical-guide-for-a-clean-architecture/   



#### CQRS
https://www.dotnetcurry.com/patterns-practices/1461/command-query-separation-cqs   

#### Design walktrough with DDD
http://www.zankavtaskin.com/2013/09/applied-domain-driven-design-ddd-part-1.html   
http://csis.pace.edu/~marchese/CS389/L8/DomainModel-UML_short.pdf   


#### DDD in Golang
https://github.com/ThreeDotsLabs/wild-workouts-go-ddd-example


```shell
# thoughts...
There are two kinds of operations assoacited with Domain Objects
- Lifecycle operations (CRUD of Account)
- Domain operations (deposit money on Account)

Lifecycle operations does not belong in the domain object such as Account. They are operations that are abstract outside
Domain operations such as "deposit(money)" would be a method on the Domain object of Account

```
