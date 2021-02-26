# Coachmatching
User models, service, repository, neo4j annotations etc.
To build a recommender system for coachees based on features in neo4j first we need to build a spring boot application with the required dependencies and data models of user(coachee) and coach. 

To connect to a neo4j instance using spring boot application we can either use neo4j desktop or sandbox or host a neo4j instance in a container in docker.

Start.spring.io is used to generate a maven project with spring boot 2.4.3 version tools and meaningful metadata tags like group id: uexcelerate and artifiact id:coachmatching.

Then using any appropriate Eclipse or intellij IDE we open the generated project in the explorer and add following packages:
Models
Repository
Resource
Service

In the model package we are going to create Users and Coaches along with their properties and the relationship that users rate the coaches according to properties.

To use springmvc we add @RestController in both data models and rest  endpoint of (rest/neo4j/user) using @RequestMapping.Also i will add a constructor to both models and also add getters to get the features. 

In order to make it compatible with neo4j we need to add @NodeEntity and annotate the class also we have to use @GraphId to mention the identifier along the first id. 
Using @Relationship in coach class we mention the list of coaches and using type=”rated” specifying each user has rated these coaches based on properties and that  the direction of relationship is incoming.
In the UserResource we autowire the UserService

