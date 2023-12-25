 question 1 
 part b 

 #include <iostream>
using namespace std;

// Abstract base class
class Shape {
public:
    virtual void draw() = 0;
};

// Derived class 1
class Circle : public Shape {
public:
    void draw() {
        cout << "Drawing Circle" << endl;
    }
};

// Derived class 2
class Square : public Shape {
public:
    void draw() {
        cout << "Drawing Square" << endl;
    }
};

int main() {
    Shape* shape1 = new Circle();
    Shape* shape2 = new Square();
    
    shape1->draw(); // Drawing Circle
    shape2->draw(); // Drawing Square
    
    delete shape1;
    delete shape2;
    
    return 0;
}



question 2 



Sol:



#include <iostream>

using namespace std;



class Product {

public:

    int productId;

    string productName;

    double price;



    Product(int id, string name, double price) {

        this->productId = id;

        this->productName = name;

        this->price = price;

    }



    void displayDetails() {

        cout << "Product ID: " << productId << endl;

        cout << "Product Name: " << productName << endl;

        cout << "Price: $" << price << endl;

    }

};



class ShoppingCart {

private:

    vector<Product> products;



public:

    void addProduct(Product product) {

        products.push_back(product);

    }



    void displayProducts() {

        for (Product product : products) {

            product.displayDetails();

        }

    }

    double calculateTotalCost() {

        double totalCost = 0;

        for (Product product : products) {

            totalCost += product.price;

        }

        return totalCost;

    }

};



class User {

public:

    int userId;

    ShoppingCart* shoppingCart;  

    User(int userId) {

        this->userId = userId;

        this->shoppingCart = nullptr;  

    }



    void createShoppingCart() {

        shoppingCart = new ShoppingCart();  

    }



    void displayUserDetails() {

        cout << "User ID: " << userId << endl;

        if (shoppingCart != nullptr) {

            cout << "Shopping Cart:" << endl;

            shoppingCart->displayProducts();

            cout << "Total Cost: $" << shoppingCart->calculateTotalCost() << endl;

        } else {

            cout << "No shopping cart associated." << endl;

        }

    }

};



int main() {



    Product book(101, "The C++ Programming Language", 49.99);

    User user1(1234);



    user1.createShoppingCart();



    user1.shoppingCart->addProduct(book);



    user1.displayUserDetails();



    return 0;

}

