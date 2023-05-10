# **Javascript OOP**

### **Que es la programación orientada a objetos?**

_La programación orientada a objetos es un paradigma de programación que se centra en las clases y los objetos. La POO utiliza objetos como elementos fundamentales en la construcción de una solución y tiene una serie de características clave, como la herencia, la cohesión, la abstracción, el polimorfismo, el acoplamiento y el encapsulamiento. La POO tiene una serie de beneficios, como la reutilización, la escalabilidad y la eficiencia del código, pero también ha sido criticada por los desarrolladores por múltiples razones._

### **Objetos:**

```javascript
console.log(typeof "Hello World");
console.log(typeof 100);
console.log(typeof false);

console.log({});
console.log([]);

console.log(typeof new Date());
console.log(typeof new RegExp());

console.log(typeof new Number(100));
console.log(typeof new String("Hello World"));
console.log(typeof new Boolean(true));
```

---

### **Objeto Literal**

Propiedades: Pares de clave-valor

```javascript
{
    model: "Shellby Cobra",
    color: "blue",
    creationYear: 1953,
    price: 1500000
}
```

**Métodos**: Acciones de los objetos. Son funciones.

```javascript
start: function(){},
back: function(){}
```

```javascript
const user = {
  name: "Ryan",
  lastname: "Ray",
  age: 30,
  showFullName() {
    return "Ryan Ray";
  },
};
console.log(user.showFullName());
```

**This**: Haciendo referencia al mismo objeto.

```javascript
const user = {
  name: "Ryan",
  lastname: "Ray",
  age: 30,
  showFullName() {
    return this.name + " " + this.lastname;
  },
};
console.log(user.showFullName());
```

```javascript
const account = {
    number: 1564,
    amount: 100,
    deposit(quantity){
        this.amount = this.amount + quantity
    }
    withdraw(quantity){
        this.amount = this.amount - quantity
    }
}

account.deposit(100)
account.withdraw(50)
```

---

### **Constructor**

```javascript
function Person() {
  (this.name = ""),
    (this.lastname = ""),
    (this.age = 0),
    (this.showFullName = function () {
      return `${this.name} ${this.lasname}`;
    });
}

const user2 = new Person();
user2.name = "Cameron";
user2.lastname = "Howe";
console.log(user2.showFullName());
```

```javascript
const user = {
  name: "",
  lastname: "",
  age: 35,
};

console.log(Object.keys(user));
console.log(Object.values(user));
```

---

### **Prototype**

Permite agregar métodos a constructores ya existentes

```javascript
function Person(name, lastname) {
  (this.name = name),
    (this.lastname = lastname),
    (this.age = 0),
    (this.showFullName = function () {
      return `${this.name} ${this.lasname}`;
    });
}

Person.prototype.greet = function () {
  return `Hello I am ${this.name}`;
};
```

---

### **Class**

Es similar al ejemplo anterior pero utilziando la palabra reservada **_`class`_**. La diferencia es que los métodos pertenecen solo al constructor y son accesibles para todos los objetos creados.

```javascript
class Person {
  constructor(name, lastname) {
    (this.name = name), (this.lastname = lastname);
  }
  greet() {
    return `Hello I am ${this.name} ${this.lastname}`;
  }
}
```

---

## **Principios de la Programación orientada a objetos**

Principles?

- Object Oriented Languages promote: modularity & code reusability.
- There is not a specification or technical document for OOP.
- It's based from common sense from papers of early researchers.

Two accepted definitions

- Capability to model problems through objects.
- Support few principles to grant modularity and code reuse.

### Model through Objects

1. Describe reality using objects and its relationship.

- Association: Object capability to refer another object.
- Aggregation: Object capability to refer one or more independent objects.
- Composition: Object capability to refer one or more dependent objects.

2. Grant modularity & code reuse.

- Encapsulation: Capability to concentrate into a single entity data and code that manipulates it. Hidden internal details.
- Inheritance: Mechanism by which object acquires some or all features of one or more objects.
- Polymorphis: Capability to process objects differently based on their data type or structure.

---

### **_Association_**

```javascript
const john = new Person("john", "ray");
const maria = new Person("maria", "raynold");

//relation
maria.parent = john;
/*
Person{
    name: "maria",
    lastname: "raynold",
    parent: Person {name: "john", lastname: "ray"}
}
*/
```

### **_Agreggation_**

```javascript
const company = {
  name: "FK Tech",
  employees: [],
};
company.employees.push(john);
```

### **_Composition_**

Cuando un objeto tiene entre sus propiedades otros objetos, éstos últimos solo pueden ser accesibles dentro del objeto padre.

---

## **OOP PRINCIPLES**

### **_Encapsulation_**: Concentrate data and functions hiding internal details.

### **_Inheritance_**: Create a specialized object starting from a general one.

```javascript
class Person {
  constructor(name, lastname) {
    this.name = name;
    this.lastname = lastname;
  }
}

class Programmer extends Person {
  constructor(language, name, lastname) {
    super(name, lastname);
    this.language = language;
  }
}

const person = new Person("maria", "perez");
const programmer = new Programmer("joe", "mcmillan", "js");
```

### **_Polymorphism_**: Handle multiple data types uniformly.

_El polimorfismo es la capacidad de objetos de diferentes tipos de responder al mismo mensaje o método de una manera que es específica para cada tipo. En JavaScript, el polimorfismo se puede lograr de varias maneras._

```javascript
class Animal {
  speak() {
    console.log("sonido");
  }
}

class Perro extends Animal {
  speak() {
    console.log("ladrido");
  }
}

let animal = new Animal();
let perro = new Perro();

animal.speak(); // Output: sonido
perro.speak(); // Output: ladrido
```

[Fuente: FaztWeb](https://www.youtube.com/watch?v=N_t1A39IB_8&t=7406s)
