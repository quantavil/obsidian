# Index
   

" Thank You Sir, it's my pleasure to introduce myself. My name is Karan Singh Rawat.
I am from Moradabad. Currently I am in my final year pursuing B.Tech in Electronics and Communication Engineering Branch  from Greater Noida Institute of Technology.
I had completed my schooling at Modern Public School, Moradabad.
I have sharpened my skills in  Python, SQL and web dev, and I have used these skills to build and several projects  like Chess AI and  Parking Space Counter . %%I have also doing project on machine learning %%
Apart From Studies my hobbies are  listening Music , playing Chess and Cycling
Sir As a Fresher I’m very enthusiastic when it comes to work,  and I’m ready to learn and grow with your company. That’s all I have to say. Thank you! 
%%And Yes! That's it about myself %%


---
## Parking Space Counter
There are two main steps in building this parking detection model:

1.  Detecting the position of all available parking spots
2.  Identifying if a parking spot is vacant or occupied

The basic idea I used for detecting the parking spots was that all parking spot dividers here are horizontal lines and the parking spots in a column are roughly equally spaced apart. I first used [Canny edge detection](https://docs.opencv.org/3.4.3/da/d22/tutorial_py_canny.html) to get an edge image. I also[[[img46]]] masked out the area where no parking spots are present.

I then did [hough line transform](https://docs.opencv.org/2.4/doc/tutorials/imgproc/imgtrans/hough_lines/hough_lines.html) on the edge image which draws out all lines it can identify. I isolated the horizontal lines by only selecting lines with slope close to zero. 

Now we are done — We can assign each spot an ID and save its coordinates in a dictionary. (I use pickle )

Now that we have the parking map, there are a few ways I think we can identify if the spot is occupied or not:

1.  Use OpenCV to check if the pixel colour of a spot aligns with the colour of an empty parking spot. This is a simple approach but prone to errors. For example change in lighting will change the colour of an empty parking spot which will make it difficult for this logic to work through the day. -Also if is possible that the logic will confuse cars of grey colour as an empty parking spot
2.  Use object detection to identify all cars and then check if the location of the car overlaps with a parking spot. I did try this and found that object detection models that can work real time really struggle with detecting objects of small size. No more than 30% of all the cars were detected

---
## CHESS AI
Sir, my project involves developing an artificial intelligence capable of playing chess and effective1ly analyze the position. I use a combination of brute-force and selective search algorithms to achieve this goal.
The search algorithm allow program to look ahead at possible future position before deciding what moves it wants to make in current position  
I'm using the MinMax algorithm to find the best move by minimising the maximum loss. To make this even better, I decided to use the Alpha-beta algorithm, which is a variation of the Minimax search algorithm that reduces the number of nodes evaluated on a large scale.
We can visualize this algorithm as a tree data structure. Where each player has only 2 move to choose. At the end of the tree, we need to perform a static evaluation of the final nodes.
Static evaluation means that how good is position for one side without making any more move. In chess we can add up the value of remaining white pieces and subtract it from the black pieces .

---
## Sorting Algorithm Visualizer
That’s why we are making this project to let everyone understand how these algorithms work and through this project you also will get a deep understanding of such sorting algorithms.
This project will guide you step by step to complete this project and at the end of this project you will have an immense grip on some core concepts of Javascript as well. Adding this project on your resume will showcase your skills and add a great value to your profile.
This project is a good start for beginners and a refresher for professionals who have dabbled in data structures and algorithms using Javascript before and also web developers. The methodology can be applied to showcase any algorithm of one's choosing, so feel free to innovate!

---

## Why we use object-oriented programming?

Object-oriented programming is the programming paradigm that is defined using objects. Objects can be considered as real-world instances of entities like class, that have some characteristics and behaviors.  

-   OOPs helps users to understand the software easily, although they don’t know the actual implementation.
-   With OOPs, the readability, understandability, and maintainability of the code increases multifold.
-   Even very big software can be easily written and managed easily using OOPs.
### TERMINOLOGIES
-   **Class** - A class is a group of objects that share common properties and 
  behavior. It is a blueprint or template from which objects are created.  
    
-   **Object**- Object is any real-world entity that can have some characteristics or which can perform some tasks. It is also called the instance of a class

---

## What are the main features of OOPs?

### Data Abstraction

1.  Data abstraction refers to providing only essential information about the data to the outside world, hiding the background details or implementation.
2.  Hiding the implementation and displaying only the functionality to the users.

#### Advantages

1.  It reduces the complexity of viewing things.
2.  Reduces the duplication of the code

#### Real Life Example

*Consider a real-life example of a man driving a car. The man only knows that pressing the accelerators will increase the speed of the car or applying brakes will stop the car but he does not know about how on pressing the accelerator the speed is actually increasing, he does not know about the inner mechanism of the car or the implementation of the accelerator, brakes, etc in the car.*

### Encapsulation

 The basic idea of Encapsulation is to wrap up both data and methods into one single unit. The way that data and methods are organized does not matter to the end-user

#### Advantages

1.  Encapsulation protects an object from unwanted access by clients.
2.  Simplifies the maintenance of the application

#### Real Life Example

*A Real-Life Example of Encapsulation is a School Bag.*

### Polymorphism

Polymorphism is the ability to exit in many forms. We can construct various classes to have methods with the same name while creating class methods.

Polymorphism is divided into two types:  

-   **Compile Time Polymorphism** - Compile time polymorphism, also known as Static Polymorphism, refers to the type of Polymorphism that happens at compile time. What it means is that the compiler decides what shape or value has to be taken by the entity in the picture.  
    
-   **Runtime Polymorphism** - Runtime polymorphism, also known as Dynamic Polymorphism, refers to the type of Polymorphism that happens at the run time. What it means is it can't be decided by the compiler. Therefore what shape or value has to be taken depends upon the execution. Hence the name Runtime Polymorphism.

#### Advantages

1.  It helps the programmer to reuse the codes, i.e. classes once written, tested and implemented can be reused as required. Saves a lot of time.
2.  A single variable can be used to store multiple data types.

#### Real Life Example

*Like a man at the same time is a father, a husband, an employee. So the same person possesses different behavior in different situations. This is called polymorphism.*

### Inheritance

Inheritance is a feature of OOPs which allows subclasses classes to inherit properties from the parent class.  

%%Types of Inheritance

-   **Single inheritance** - When a class inherits from a single class, it is known as a single inheritance
    
-   **Multiple inheritances** - Multiple inheritances come into the picture when a class inherits from more than one base class.  
      
    Parent 1 && Parent2 → child
    
-   **Multilevel inheritance** - When there is a chain of inheritance, it is known as multilevel inheritance.  
      
    Example: Animal → Dog → Puppy  
    Puppy Inherits from the Dog Class, Dog class inherits from the Class Animal.
    
-   **Hierarchical inheritance** - When two or more classes inherit a single class, it is known as hierarchical inheritance.  
      
    Example: Animal → Dog = Cats
    
-   **Hybrid inheritance** - Hybrid inheritance is a combination of multiple and multi-level inheritances.ance** - Hybrid inheritance is a combination of multiple and multi-level inheritances.%%

#### Advantages

The main advantages of inheritance are code reusability and readability. When a child class inherits the properties and functionality of the parent class, we need not to write the same code again in the child class. This makes it easier to reuse the code, makes us write less code and the code becomes much more readable.

#### Real Life Example

*If there is a class such as ‘vehicle’, other classes like ‘car’, ‘bike’, etc can inherit common properties from the vehicle class.*


### Why OOPs is so Popular / Advantages of OOPs /Why do we need oops

1) OOP provides a clear modular structure for programs

2) OOP makes it easy to maintain and modify existing code

3) Code Reusability : We can build the programs from standard working modules that communicate with one another, rather than having to start writing the code from scratch which leads to saving of development time and higher productivity,

5) OOP language allows to break the program into the bit-sized problems that can be solved easily (one object at a time).
---

## What is Overloading and Overriding?

When two or more methods in the same class have the same name but different parameters, it's called Overloading.  

When the method name and parameters are the same in the superclass and the child class, it's called Overriding.  

---

## What is Constructor ?
Constructors are **generally used for instantiating an object**, It is a method that is called when an object is created. 

---



**Srijian** is an IT company that ranks fourth in the world in Drupal, with expertise in Drupal, Analytics & Insights, Micro services, and cloud engineering, as well as partnerships with AWS and VMware.

**why you want to join company**
With my existing skill sets in web development, I believe the work criteria for this career are a fantastic fit for me. I could see myself in that capacity because it matched my career goals, talents, and knowledge.

_adjusts in seat, maintaining a confident yet personable demeanor_

At BYJU'S, my core responsibility revolves around seamlessly integrating third-party APIs, plugins, and services into our cutting-edge e-learning platform. This involves a deep understanding of RESTful API architectures, authentication protocols like OAuth, and data interchange formats such as JSON and XML.

I leverage tools like Postman and Insomnia for API testing and debugging, while Docker and Kubernetes streamline containerization and deployment processes. Git serves as our version control system, enabling collaborative development across teams. Additionally, I work closely with product managers, designers, and QA to ensure these integrations align with our platform's functionality and user experience goals.

Certainly, in my role at BYJU'S, I've had the opportunity to integrate various third-party APIs to enhance our e-learning platform's capabilities. Some of the key APIs I've worked with include:

1. Payment Gateways: Razorpay, PayU, Stripe
2. Video Streaming: Wowza, Azure Media Services
3. Push Notifications: Firebase Cloud Messaging, Amazon SNS
4. Analytics: Google Analytics, Amplitude
5. Social Media: Facebook, Twitter, LinkedIn
6. Cloud Storage: Amazon S3, Google Cloud Storage
7. Maps and Geolocation: Google Maps, MapBox
8. Identity Management: Auth0, Firebase Authentication
9. Chatbots and Virtual Assistants: Dialogflow, Amazon Lex
