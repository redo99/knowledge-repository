### Les commandes JDK
- java: Interprète, permet de lancer un programme Java avec la *machine virtuelle*. `java Test.class`
- javac: compilateur, permet de transformer le code java en bytecode. `javac Test.java`
- javadoc: Permet de générer la documentation Java
- jar: Permet de créer des fichiers `jar jar -cf Test.jar com/metc/Test.class`.

### Les classes

#### Les classes anonymes
- Une classe anonyme est une classe définit au sein d'une methode. Elle n'a pas de nom et sa déclaration fusionne avec son instanciation. Elle implémente une interface ou hérite d'une classe. 

```Java
class InterfaceSample {
  public static void main(String[] args) {
    /* Ceci est un passage de traitement en paramètre via une classe anonyme. */
    printYear(new MySuperInterface() {
      @Override
      public int getYear() {
        return 1999;
      }
    });
  }

  public static void printYear(MySuperInterface myInterface) {
    System.out.println(myInterface.getYear());
  }
}

interface MySuperInterface {
  int getYear();
}
```
```Java
class ClassSample {
  public static void main(String[] args) {
    /** Ceci est un passage de traitement en parametre via une classe anonyme. */
    printYear(new MySuperClass() {
      @Override
      public int getYear() {
        return 1999;
      }
    });
  }

  public static void printYear(MySuperClass myClass) {
    System.out.println(myClass.getYear());
  }
}

class MySuperClass {
  int getYear() {
      return 2000;
  }
}
```

### Les methodes

- Les arguments d'une methode sont des constantes.
  Nous ne pouvons pas changer leur valeur mais nous pouvons changer leurs attributs.

### Les collections

- Les tableaux (array) : La taille du tableau est définie a l'initialisation.
```Java
int[] intArray = new int[3];
```
ou
```Java
int[] intArray = {10, 8, 21};
```
Les tableaux multidimensionnels se declarent ainsi
```Java
String[][] myTheatreSeats=new String[30][12];
```
- Les Listes (List) : collection d'objets ***ordonnés***

- Les Ensembles (Set) : collection d'objets ***uniques*** et ***non ordonnés***
  `/!\ Lors de l'ajout d'un objet deja existant dans un Set, aucune exception n'est levée mais l'ajout ne s'effectue pas.`

- Les dictionnaires (Map) : Collection de paires clé/valeur. La classe HashMap n'insert pas forcément dans l'ordre,
  pour preserver l'ordre il faut utiliser la classe LinkedHashMap.

### Les boucles

- Les boucles d'enumeration (for):
```java
for(i = 0; i < 10; i++){
  Sytem.out.println("I'm so happy");
}
```
```java
String[] array = {"String1", "String2", "String3"};
for(int i = 0; i < array.length; i++){
    System.out.println(array[i]);
}
```
```java
String[] array = {"String1", "String2", "String3"};
for(String text : array){
    System.out.println(text);
}
```

- les boucles conditionnelles (while):
```java
String[] array = {"String1", "String2", "String3"};
int i = 0;
while(i < array.length) {
    System.out.println(array[i]);
    i++;
}
```
```Java
String[] array = {"String1", "String2", "String3"};
int i = 0;
do {
  System.out.println(array[i]);
  i++;
} while(i < array.length);
```

```java
Stream<T> filter(Predicate<? super T> predicate);
```