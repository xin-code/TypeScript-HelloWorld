## 简介

1. **TypeScript**是**JavaScript**的**超集**。

2. TypeScript 其实就是类型化的 JavaScript，它不仅支持 JavaScript 的所有特性，还在 JavaScript 的基础上添加了**静态类型注解扩展**。
3. 相较于JS而言，TS拥有了静态类型，更加严格的语法，更强大的功能；TS可以在代码执行前就完成代码的检查，减小了运行时异常的出现的几率；TS代码可以编译为任意版本的JS代码，可有效解决不同JS运行环境的兼容问题；同样的功能，TS的代码量要大于JS，但由于TS的代码结构更加清晰，变量类型更加明确，在后期代码的维护中TS却远远胜于JS。
4. TS代码需要通过编译器编译为JS`（使用 "tsc xx.ts“ 文件 即可编译为js文件）`，然后再交由JS解析器执行。



### Hello World

```typescript
function greeter(person) {
  return 'Hello, ' + person;
}

let user = 'Xin';

console.log(greeter(user));
// Hello, Xin
```



### 类型注解

- 类型注解是一种轻量级的为函数或变量添加约束的方式。

```typescript
function greeter(person: string) {
  return 'Hello,' + person;
}

let user = [1, 2, 3];

console.log(greeter(user));
// 报错，因为 greeter 类型注解写了是String形的，传入数组类型即报错
```





### 接口

- 使用接口描述一个对象内拥有2个String的字段

```typescript
interface Person {
  firstName: string;
  lastName: string;
}

function greeter(person: Person) {
  return 'Hello, ' + person.firstName + ' ' + person.lastName;
}

let user = { firstName: 'John', lastName: 'User' };

console.log(greeter(user));
// Hello, John User
```



### 类

```typescript
class Student {
  fullName: string;
  constructor(public name, public email, public age) {
    this.fullName = name + ' ' + email + ' ' + age;
  }
}

interface Person {
  name: string;
  age: number;
}

function greeter(student: Person) {
  return 'Hello, ' + student.name + ' ' + student.age;
}

let user = new Student('张三', '123456@gmail.com', 22);

console.log(greeter(user));
// Hello, 张三 22
```

