Type Narrowing in TypeScript

Introduction: 
Type narrowing is an important TypeScript feature that helps developers work safely with variables that can have multiple types. It allows TypeScript to determine a more specific type within a particular block of code. This reduces runtime errors and improves type safety.

Detailed Explanation :
One common narrowing technique is typeof. It checks the primitive type of a variable and allows TypeScript to handle each possibility separately.

function processValue(value: string | number): string | number {
  if (typeof value === "string") {
    return value.toUpperCase();
  }

  return value * 2;
}

Another technique is instanceof. It checks whether an object belongs to a particular class.

typescript
class Dog {
  bark(): string {
    return "Woof!";
  }
}

class Cat {
  meow(): string {
    return "Meow!";
  }
}

function makeSound(animal: Dog | Cat): string {
  if (animal instanceof Dog) {
    return animal.bark();
  }

  return animal.meow();
}


The in operator checks whether a property exists in an object. It is especially useful when working with different object structures.

typescript
type Admin = {
  name: string;
  permissions: string[];
};

type Customer = {
  name: string;
  purchases: number;
};

function getInfo(user: Admin | Customer): string {
  if ("permissions" in user) {
    return user.permissions.join(", ");
  }

  return `Purchases: ${user.purchases}`;
}

Conclusion

Type narrowing makes TypeScript applications safer and easier to maintain. Using typeof, instanceof, and the in operator helps developers handle union types correctly. Understanding these techniques is essential for writing reliable TypeScript code.
