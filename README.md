# Activity 25: SOLID PRINCIPLES IN ANGULAR

## 1. Single Responsibility Principle (SRP)
Definition: A class should have one, and only one, reason to change. It should have only one job or responsibility.

Example:

 ``` typescript
# Violating SRP
class User:
    def __init__(self, name):
        self.name = name
    
    def save(self):
        # Saving user to DB
        pass
    
    def send_email(self):
        # Sending email to user
        pass
```
Explanation: The User class now only focuses on user data, while UserRepository handles persistence and EmailService handles communication. This separation improves maintainability and testing.

 ## 2. Open/Closed Principle (OCP)
Definition: Software entities (classes, modules, functions) should be open for extension, but closed for modification.

Example:

 ``` typescript
# Violating OCP
class Payment:
    def process_payment(self, amount, method):
        if method == "credit_card":
            # process credit card payment
            pass
        elif method == "paypal":
            # process PayPal payment
            pass
```
Explanation: The Payment class is now closed for modification but open for extension. Adding new payment methods (e.g., BankTransferPayment) doesn't require changing existing code; you just extend PaymentMethod.

## 3. Liskov Substitution Principle (LSP)
Definition: Objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program.

Example:

 ``` typescript
class Bird:
    def fly(self):
        pass

class Penguin(Bird):  # Violates LSP
    def fly(self):
        raise Exception("Penguins can't fly!")
 ```
Explanation: The move() method provides a common abstraction. Subclasses now follow the Liskov principle by ensuring that substituting one class for another doesn't break the behavior expected from Bird.

## 4. Interface Segregation Principle (ISP)
Definition: Clients should not be forced to depend on interfaces they do not use.

Example:

 ``` typescript
class Worker:
    def work(self):
        pass
    def eat(self):  # Violates ISP
        pass

class Manager(Worker):
    def work(self):
        # Managing tasks
        pass
    def eat(self):
        # Eating during break
        pass

class Developer(Worker):  # Developer shouldn't need eat method
    def work(self):
        # Writing code
        pass
 ```
Explanation: Manager and Developer now implement only the relevant interfaces (Workable and Eatable). This avoids forcing Developer to depend on the eat method they don't need.

## 5. Dependency Inversion Principle (DIP)
Definition: High-level modules should not depend on low-level modules. Both should depend on abstractions. Furthermore, abstractions should not depend on details. Details should depend on abstractions.

Example:

 ``` typescript
class LightBulb:
    def turn_on(self):
        pass

    def turn_off(self):
        pass

class Switch:
    def __init__(self, bulb: LightBulb):
        self.bulb = bulb

    def operate(self):
        # Control the bulb's state
        self.bulb.turn_on()
 ```
Explanation: Now, Switch depends on the abstraction Switchable instead of directly on LightBulb. This allows Switch to control any Switchable device, promoting flexibility and easier changes.


##  Hashnode Link :

https://viernes.hashnode.dev/activity-25-solid-principles-in-angular



















































