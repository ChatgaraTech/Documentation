  
## 🎬 Description


> Petite documentation faisant référence à la video sur le sujet présent sur la chaine ChatgaraTech

---
## ☕ Java 8

### 🔹 Lambda Expressions

> Ce sont les fonctions anonymes de java

```java
List<String> names = Arrays.asList("Alice", "Bob", "Charlie");
names.forEach(name -> System.out.println(name));
```
### 🔹 Stream API

> Cela permet de traiter des collections avec des opérations comme map, filter ou reduce

```java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
int sum = numbers.stream()
                 .filter(n -> n % 2 == 0)
                 .mapToInt(Integer::intValue)
                 .sum();
System.out.println(sum);  // Affiche 6
```
### 🔹 Interfaces Fonctionnelles

> Ce sont des interface possédant une méthode abstraite, l'implémentation étant réalisé via des lambda expression

```java
@FunctionalInterface
interface Greeting {
    void sayHello(String name);
}

Greeting greet = name -> System.out.println("Hello " + name);
greet.sayHello("Java");
```

### 🔹 Méthodes par défaut dans les interfaces

> Permet simplement d'ajouter des comportements par défaut au niveau des interfaces

```java
interface Vehicle {
    void start();

    default void honk() {
        System.out.println("Beep beep!");
    }
}

class Car implements Vehicle {
    public void start() {
        System.out.println("Car started");
    }
}

Car car = new Car();
car.start();  // Car started
car.honk();   // Beep beep!

```
### 🔹 Optional

> Il s'agit d'une nouvelle classe pouvant contenu une valeur, utile pour éviter les NullPointerException

```java
Optional<String> optional = Optional.ofNullable(null);
System.out.println(optional.orElse("Valeur par défaut"));  
// Affiche "Valeur par défaut"
```

---
## ☕ Java 9

### 🔹 Méthodes privées dans les interfaces

> Cela permet simplement d'aider à la factorisation du code

```java
interface Logger {
    private void log(String msg) {
        System.out.println("Log: " + msg);
    }
    default void info(String msg) {
        log("INFO: " + msg);
    }
    default void error(String msg) {
        log("ERROR: " + msg);
    }
}

class AppLogger implements Logger {}

AppLogger logger = new AppLogger();
logger.info("Application démarrée");  // Log: INFO: Application démarrée
```

---
## ☕ Java 10

### 🔹 Mot-clé `var`

>Permet d’inférer le type d’une variable locale à partir de sa valeur d'initialisation.

```java
var message = "Bonjour Java 10!";
System.out.println(message);
```

---
## ☕ Java 11

### 🔹 `var` dans les lambdas

> Avec Java 11, on peut désormais utiliser les var dans les paramètres de lambda

```java
List<String> list = Arrays.asList("Java", "Python");
list.forEach((var s) -> System.out.println(s.toUpperCase()));
```
### 🔹 Nouvelles méthodes `String`

```java
String text = "  Hello Java 11  ";
System.out.println(text.isBlank());          // false
System.out.println("   ".isBlank());         // true
text.lines().forEach(System.out::println);   // affiche la chaîne ligne par ligne
System.out.println(text.strip());             // "Hello Java 11"
System.out.println(text.stripLeading());      // "Hello Java 11  "
System.out.println(text.stripTrailing());     // "  Hello Java 11"
System.out.println("ha".repeat(3));           // "hahaha"
```
### 🔹 Http Client

> Il s'agit d'une toute nouvelle API moderne et asynchrone permettant de faire des requêtes HTTP, remplace notamment l'utilisation de HttpURLConnection

```java
HttpClient client = HttpClient.newHttpClient();
HttpRequest request = HttpRequest.newBuilder()
    .uri(URI.create("https://example.com"))
    .build();

client.sendAsync(request, HttpResponse.BodyHandlers.ofString())
    .thenApply(HttpResponse::body)
    .thenAccept(System.out::println);
```

---
## ☕ Java 14

### 🔹 `yield` dans `switch`

> Permet de retourner directeur une valeur depuis un bloc switch

```java
String day = "LUNDI";
String type = switch (day) {
    case "SAMEDI", "DIMANCHE" -> "weekend";
    default -> {
        yield "jour de semaine";
    }
};
System.out.println(type);  // jour de semaine
```
### 🔹 NullPointerException plus verbeux

>Une nouvelle fonctionnalité permet de rendre les NullPointerException moins flou :

```bash
java -XX:+ShowCodeDetailsInExceptionMessages ExempleNPE
```

> Prenons le code suivant

```java
System.out.println(p.adresse.ville);
```

>Avant on devait deviner si p, p.adresse ou p.adresse.ville était null

>Sans l'option
```java
Exception in thread "main" java.lang.NullPointerException
    at ExempleNPE.main(ExempleNPE.java:14)
```

>Avec -XX:+ShowCodeDetailsInExceptionMessages
```java
Exception in thread "main" java.lang.NullPointerException: Cannot read field "ville" because "p.adresse" is null
    at ExempleNPE.main(ExempleNPE.java:14)
```


---
## ☕ Java 15

### 🔹 Text Blocks (multi-ligne)

> Permet d'écrire de chaine de caractères multi-ligne de manière lisible


```java
String json = """
{
  "name": "Java",
  "version": 15
}
""";
System.out.println(json);
```

## ☕ Java 16

### 🔹 Pattern Matching avec `instanceof`

> Permet de faire un cast automatique + déclaration directement dans un bloc if

Avant
```java
Object obj = "Hello";
if (obj instanceof String) {
    String s = (String) obj;
    System.out.println(s.toUpperCase());
}
```

Après 
```java
Object obj = "Hello";
if (obj instanceof String s) {
    System.out.println(s.toUpperCase());
}
```
### 🔹 Records

> Facilite la création de classe de données immuable et génère automatiquement les equals, hascode et toString

```java
record Person(String name, int age) {}

Person p = new Person("Alice", 30);
System.out.println(p.name());  // Alice
System.out.println(p);         // Person[name=Alice, age=30]
```

---
## ☕ Java 17

### 🔹 Sealed Classes

> Permet de restreindre quelles classes peuvent hériter d'une classe ou implémenter une interface

```java
public abstract sealed class Shape permits Circle, Rectangle {}

final class Circle extends Shape {}
final class Rectangle extends Shape {}
// Pas possible d’étendre Shape en dehors des classes listées
```

---
## ☕ Java 21

### 🔹 Pattern Matching pour `switch`

> Permet d'appliquer des patterns (comme instanceof) directement dans les switch

```java
Object obj = "Java";

String result = switch (obj) {
    case String s -> "C’est une chaîne : " + s;
    case Integer i -> "C’est un entier : " + i;
    default -> "Autre type";
};

System.out.println(result);
```
### 🔹 Record Pattern

```java
sealed interface Event permits Payment, Refund {}

record Payment(String userId, double amount) implements Event {}
record Refund(String userId, double amount, String reason) implements Event {}

public class EventProcessor {
    public static void processEvent(Event event) {
        switch (event) {
            case Payment(String userId, double amount) ->
                System.out.println("Paiement reçu");

            case Refund(String userId, double amount, String reason) ->
                System.out.println("Remboursement reçu");

            default ->
                System.out.println("Type d'événement inconnu.");
        }
    }
```

---
## ⚙️ Autres améliorations notables

- ✅ Améliorations de performance (exécution, GC)
- ✅ Mises à jour de sécurité régulières

---
## 📚 Sources

- https://www.baeldung.com/java-11-new-features  
- https://www.baeldung.com/java-17-new-features  
- https://gpiskas.com/posts/java-8-to-java-21-new-language-features-highlights/  
- https://openjdk.org/projects/jdk8/features  
- https://openjdk.org/projects/jdk9/  
- https://openjdk.org/projects/jdk/10/  
- https://openjdk.org/projects/jdk/11/  
- https://openjdk.org/projects/jdk/17/jeps-since-jdk-11  
- https://openjdk.org/projects/jdk/21/jeps-since-jdk-17
