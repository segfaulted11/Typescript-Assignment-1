Access Modifiers in TypeScript

Introduction :
Access modifiers in TypeScript are used to control the visibility and accessibility of class properties and methods. They help protect data, improve code organization, and support the principles of Object-Oriented Programming (OOP). TypeScript provides three main access modifiers: public, private, and protected. It also supports readonly properties.

Detailed Explanation :

The public modifier allows a property or method to be accessed from anywhere. It is the default access modifier in TypeScript.

class Student {
  public name: string = "Rakib";
}

const student = new Student();
console.log(student.name);

The private modifier restricts access to the class where the property or method is declared. It cannot be accessed directly from outside the class or its subclasses.

class Account {
  private balance: number = 5000;

  getBalance(): number {
    return this.balance;
  }
}

The protected modifier allows access within the declaring class and its subclasses, but not from external objects.

class Employee {
  protected name: string = "Alice";
}

class Manager extends Employee {
  getName(): string {
    return this.name;
  }
}

The readonly modifier allows a property to be assigned only during declaration or inside the constructor. After initialization, its value cannot be changed.

class Product {
  readonly id: number = 101;
}

Conclusion :
Access modifiers help developers control data access and maintain secure, organized code. Using public, private, protected, and readonly appropriately makes TypeScript applications easier to manage, maintain, and extend.
