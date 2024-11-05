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













