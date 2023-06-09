## A04

- Name: Dayton Parsons
- Date: 05 1 23
- Class: 2143 OOP

## Definitions

#### Abstraction 

> abstraction is a useful concept to help us focus a problem while hiding the implementation aspect that is not of current use. 
> can be achieved through encapsulation, inheritance, and polymorphism. 

><![image](https://user-images.githubusercontent.com/123118802/236091364-acd1c1fc-ee47-4a09-8ee0-b5cf887c84b5.png)



#### Attributes/Properties 

> attributes and properties are used to give objects (entities) a description

>class Rectangle {
   public:
      int width;
      int height;
    };
    
> in the above code width and height are attributes/properties

>![image](https://user-images.githubusercontent.com/123118802/236092749-ef0cf38b-ee79-4ead-8fb6-e3516ce19a58.png)



#### Class

><img src="https://ds055uzetaobb.cloudfront.net/image_optimizer/722c82aff075a14313be7fa7463f7fedad151a0a.png" width=250>




#### Object
> shown in the above picture objects are essentially an instance of a given class, so the three types of cars
> polo, mini, and beetle are objects of the class "car"



#### Method
    >>class Car {
     public:
    string make;
    string model;
    int year;

    void start() {
        cout << "The " << make << " " << model << " has started." << endl;
    }

    void stop() {
        cout << "The " << make << " " << model << " has stopped." << endl;
    }

    void drive() {
        cout << "The " << make << " " << model << " is driving." << endl;
    }
    };

     int main() {
     Car mini;
     mini.make = "Mini";
     mini.model = "Cooper S";
     mini.year = 2022;

    Car polo;
    polo.make = "Volkswagen";
    polo.model = "Polo GTI";
    polo.year = 2021;

    Car beetle;
    beetle.make = "Volkswagen";
    beetle.model = "Beetle";
    beetle.year = 2020;

    mini.start();
    polo.drive();
    beetle.stop();

    return 0;
    }
> the above code shows us how we can use methods to put our class and our objects to use!
> essentially metohds are defined within a class and used to perform operations on the objects within that class. 
> they can also be reffered to as member functions. 


#### Class Variable/Static
> class variable or static data member is created inside the class with the keyword "static"
> it is stored in memory once for the entire class rather than once for each object. 
> if we want to add a static memeber to our above car class ^^ we can do so like this 

    
   
    class Car {
      public:
    string make;
    string model;
    int year;
    static int count;
    

    Car(string m, string mdl, int y) {
        make = m;
        model = mdl;
        year = y;
        count++;
    }

    static void displayCount() {
        cout << "There are " << count << " cars." << endl;
    }
    };
    
#### Composition 
>composition is when a subckass contains an object or objects, of another class as its member variables. 
>if we use the same class "car" that we have been using for these definitions. we can add onto it to show composition. if we were to make class called "Engine" like this. 

    class Engine {
    public:
    void start() {
        cout << "Engine started." << endl;
    }

    void stop() {
        cout << "Engine stopped." << endl;
    }
    };
    
>we can add a data type of type "Engine" called "engine" into our Car class and have member functions to start and stop the enginer and that would be an example of composition. 
    
    class Car {
    public:
    Engine engine; 
    
    void start() {
        engine.start();
    }

    void stop() {
        engine.stop();
    }

#### Encapsulation / Public, Private, and Protected 
>Encapsulation is how we can control access to our data in a class/struct. A class is Private by default but a struct is Public by default. 
>That's why we have to be careful when creating a class or struct. I will give a code example below of how we use Encapsulation in a class. 

    class Car {
    private:
    string make;
    string model;
    int year;

    public:
    Car(string m, string mdl, int y) {
        make = m;
        model = mdl;
        year = y;
     }

    void display() {
        cout << year << " " << make << " " << model << endl;
    }

    void setYear(int y) {
        year = y;
    }

    int getYear() {
        return year;
    }
    };

    int main() {
    Car c("Mini", "Cooper S", 2022);

    c.display();

    //c.make = "Volkswagen"; // This line will cause a compile-time error
    c.setYear(2023);
    cout << "New year: " << c.getYear() << endl;

    return 0;
> This demonstrates Encapsulation in action and shows how the details of "Car" are hidden from outside code. 

