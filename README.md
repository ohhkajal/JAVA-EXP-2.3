# JAVA-EXP-2.3
Java programs using lambda and streams simplify sorting and data processing. Employees can be sorted by name, age, or salary using lambdas. Students scoring above 75% are filtered and sorted by marks using streams. Products are grouped by category, with max price and average calculated efficiently.
### **Java Programs Using Lambda Expressions and Stream Operations**

---

#### **Part A: Sorting Employee Objects Using Lambda Expressions**

**Objective:**
Develop a Java program to sort a list of `Employee` objects by **name**, **age**, or **salary** using lambda expressions.

**Explanation:**
Lambda expressions make sorting logic concise and readable.
Steps:

1. Create an `Employee` class with `name`, `age`, and `salary`.
2. Store multiple employees in a `List<Employee>`.
3. Use `Collections.sort()` or `List.sort()` with lambdas:

   * Sort by **name** → `e1.name.compareTo(e2.name)`
   * Sort by **age** → `Integer.compare(e1.age, e2.age)`
   * Sort by **salary** (descending) → `Double.compare(e2.salary, e1.salary)`

This demonstrates functional-style sorting.

**Example Code:**

```java
employees.sort((e1, e2) -> e1.name.compareTo(e2.name));
employees.sort((e1, e2) -> Integer.compare(e1.age, e2.age));
employees.sort((e1, e2) -> Double.compare(e2.salary, e1.salary));
```

---

#### **Part B: Filtering and Sorting Students Using Streams**

**Objective:**
Use streams and lambdas to filter students scoring **above 75%**, sort them by marks, and display names.

**Explanation:**
This part applies functional-style filtering and sorting:

1. Create a `Student` class with `name` and `marks`.
2. Store objects in `List<Student>`.
3. Use stream operations:

   * `filter(s -> s.marks > 75)`
   * `sorted((s1, s2) -> Double.compare(s1.marks, s2.marks))`
   * `map(s -> s.name)` and `forEach(System.out::println)`

**Example Code:**

```java
students.stream()
        .filter(s -> s.marks > 75)
        .sorted((a, b) -> Double.compare(a.marks, b.marks))
        .map(s -> s.name)
        .forEach(System.out::println);
```

---

#### **Part C: Stream Operations on Product Dataset**

**Objective:**
Use Java Streams to group, find max, and calculate averages for products.

**Explanation:**

1. Create a `Product` class with `name`, `price`, and `category`.
2. Use stream operations:

   * `groupingBy(Product::getCategory)`
   * `maxBy(Comparator.comparingDouble(Product::getPrice))`
   * `averagingDouble(Product::getPrice)`

**Example Code:**

```java
products.stream().collect(Collectors.groupingBy(p -> p.category));
products.stream().collect(Collectors.groupingBy(p -> p.category,
       Collectors.maxBy(Comparator.comparingDouble(p -> p.price))));
double avg = products.stream().collect(Collectors.averagingDouble(p -> p.price));
```

---

**Summary:**
These programs demonstrate how **lambda expressions** and **stream APIs** simplify sorting, filtering, and data processing—making Java code cleaner, functional, and efficient.

