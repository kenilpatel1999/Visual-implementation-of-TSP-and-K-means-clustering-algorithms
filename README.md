# Visual-implementation-of-TSP-and-K-means-clustering-algorithms

The main for purpose of this project was to learn the implementation of different design patterns for the common problems occure in software design.

## How To Use The Application
- To create a city, select 'create' from 'Action' menubar.
- When you have created enough cities, select the algorithm you want to run.
- Once the algorithm is finished running, you will be able to see the results.
- To move the cities, select 'move' from 'Action' menubar. Now, you can play with it 😜.
- By selecting 'connect' in 'Action' menubar, you can connect the unconnected cities as you please.
- 'User Connect' in 'Connection' erases all the previous connections and you connect the cities independently.
- You can right-click on any city and change its shape, size, or color from the options.

## Implemented Design Patterns

###### Observer Pattern
- In the project, there are 6 classes, Main, Workspace, TSPNN, KMeans, and City. The Workspace class is used to create the GUI, and TSPNN, KMeans is our logic/implementation/algorithm classes. 
- TSP and K-Means clustering are the two algorithms used in the project. When TSP is selected, the algorithm finds the shortest possible route that visits each city exactly once and returns to the origin city. When K-Means is selected, the algorithm creates the clusters based on the user input.
- The observer pattern is the best fit here. The Workspace class implements the Observer interface and the TSPNN and Kmeans classes extend the Observable class. 
- So, when a new city is added or any city is dragged from one place to another (i.e when data is changed), it will call the selected algorithm. Once the selected algorithm is executed completely, it will notify the Workspace class and the Workspace class will update the data changes in GUI.

###### Singleton Pattern
- In this project, for certain classes, there was a need to create different objects of the same class and need all of them to share the information. Singleton pattern allows the class to create multiple objects and let them share the same data. I have implemented a singleton pattern for Blackboard, TSPNN, FactoryCity, FactoryConnections, MessageDisplayer classes. In the background, there are multiple references for the same Object.

###### Chain of Responsibility:
- There are two separate classes for two different algorithms. Both are needed to be called by the class ‘Workspace’. This increases the coupling between the Workspace class and the algorithm classes. Chain of Responsibility helps reduce the coupling by giving more than one object a chance to handle the request (i.e it selects one algorithm at a time). 
- In this project, I have implemented the chain of responsibility for classes TSPNN and KMeans. Here, these classes implement a Handler interface which results in overriding the HadleRequest method.

###### Decorator Pattern:
- Right-clicking on the city will open a dialog box to decorate the square with different shapes (shapes are a basic square with a circle inside or square surrounding other squares and circle inside a square and surrounded by other squares), colors, or change the size of the square. The decorator pattern decorates the basic object with other objects.
- To implement it, there are two basic shapes, square and circle, which implement the Shape interface. The ShapeDecorator class also implements the Shape interface. There are three more decorator classes CircleSquareDecorator, CircleSquareGroupDecorator, and SquareGroupDecorator which extends the ShapeDecorator class.

###### Factory Pattern:
- A factory pattern is used when we do not want to expose the creational logic of the object, where it is used· In this project, it was implemented to create the objects of the classes City and Connection.
- The class FactoryCity which implements The Factory interface and the object of class City is only created in class FactoryCity. The same goes for the implementation of the factory pattern for class Connection. The class FactoryConnections implements the FactoryForConnection interface and the object of class Connection is only created in class FactoryConnections.


## References
https://github.com/psyclone20/k-means-clustering: for the clustering algorithm.
