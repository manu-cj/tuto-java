# tutoriel-java

# 🚀 TUTO COMPLET – LES FONDAMENTAUX DE JAVA

## 1. ⚙️ Syntaxe de base

```java
public class Main {    
	public static void main(String[] args) {        
		System.out.println("Hello world !");    
	}
}
```

## 2. 🧮 Variables et types

```java
int age = 25;
double prix = 19.99;
boolean estActif = true;
char lettre = 'A';
String nom = "Manu";
```

- **Types primitifs** : `int`, `double`, `boolean`, `char`
- **Types objets** : `String`, `Scanner`, `ArrayList`, etc.

## 3. 🔁 Conditions et boucles

### If / else

```java
if (age >= 18) {    
	System.out.println("Majeur");
} 
else {    
	System.out.println("Mineur");
}
```

### Switch

```java
int choix = 2;

switch (choix) {    
	case 1 -> System.out.println("Un");    
	case 2 -> System.out.println("Deux");    
	default -> System.out.println("Autre");
}
```

### Boucles

```java
for (int i = 0; i < 5; i++) {    
	System.out.println(i);
}

int i = 0;while (i < 5) {    
	System.out.println(i);
  i++;
}
```

## 4. 📦 Tableaux (arrays)

```java
int[] notes = {12, 15, 8};
```

```java
for (int i = 0; i < notes.length; i++) {    
	System.out.println(notes[i]);
}
```

```java
for (int note : notes) {    
	System.out.println(note);
}
```

## 5. 🧱 Classes, objets et constructeurs

```java
public class Personne {
    String nom;
    int age;   
    
    public Personne(String nom, int age) { 
        this.nom = nom;        
        this.age = age;    
     }}
```

```java
Personne p = new Personne("Manu", 25);
```

## 6. 🔄 Méthodes

```java
public class MathUtil {    
	public static int doubler(int x) {        
			return x * 2;    
	}
}
```

```java
int resultat = MathUtil.doubler(5); // 10
```

## 7. 🧬 Héritage

```java
class Animal {    
	void parler() {        
		System.out.println("Je suis un animal");    
	}
}

class Chien extends Animal {    
	void parler() {        
		System.out.println("Wouf !");    
	}
}
```

```java
Animal a = new Chien();
a.parler(); // "Wouf !"
```

## 8. 🧩 Interface

- Interface = contrat
- Classe = comportement

## 9. 🛠️ Modificateurs d’accès

| Modificateur | Accessible depuis… |
| --- | --- |
| public | Partout |
| private | Dans la classe uniquement |
| protected | Dans le même package ou sous-classe |
| (aucun) | Dans le même package uniquement |

## 10. 📚 Packages & Imports

```java
import java.util.Scanner;
```

### Créer un package perso

```java
package com.manu.utils;

public class Util {    
	public static void salut() {        
		System.out.println("Salut !");    
	}
}
```

## 11. 🧰 Collections

### ArrayList

```java
import java.util.ArrayList;

ArrayList<String> noms = new ArrayList<>();

noms.add("Manu");
noms.add("Paul");

for (String nom : noms) {    
	System.out.println(nom);
}
```

### HashMap

```java
import java.util.HashMap;

HashMap<String, Integer> scores = new HashMap<>();

scores.put("Manu", 15);
scores.put("Paul", 18);

System.out.println(scores.get("Manu")); // 15
```

## 12. 🧨 Exceptions

```java
try {    
	int res = 10 / 0;
} 
catch (ArithmeticException e) {    
	System.out.println("Erreur : division par zéro !");
}
```

## 13. 🧼 Bonnes pratiques

- Utiliser des noms clairs
- Découper en petites méthodes
- Éviter la duplication
- Commenter si nécessaire
- Toujours définir les modificateurs d’accès

## 🧪 En résumé

| Élément | Ce que ça fait |
| --- | --- |
| class | Plan pour créer un objet |
| interface | Contrat de méthodes |
| object | Instance d’une classe |
| array | Tableau de taille fixe |
| ArrayList | Liste dynamique |
| extends | Hérite d’une classe |
| implements | Implémente une interface |
| import | Utilise une classe externe |
| package | Organise ton code |
| try/catch | Gère les erreurs |

## 14. 📖 Scanner et Fichiers

### Scanner - Lecture depuis console

```java
import java.util.Scanner;

Scanner scanner = new Scanner(System.in);

System.out.print("Entrez votre nom : ");
String nom = scanner.nextLine();

System.out.print("Entrez votre âge : ");
int age = scanner.nextInt();

scanner.close();
```

### Lecture de fichier

```java
import java.io.File;
import java.io.FileReader;
import java.io.BufferedReader;

try {
    File fichier = new File("texte.txt");
    BufferedReader lecteur = new BufferedReader(new FileReader(fichier));
    
    String ligne;
    while ((ligne = lecteur.readLine()) != null) {
        System.out.println(ligne);
    }
    
    lecteur.close();
} catch (Exception e) {
    System.out.println("Erreur : " + e.getMessage());
}
```

### Écriture dans un fichier

```java
import java.io.FileWriter;
import java.io.BufferedWriter;

try {
    FileWriter fw = new FileWriter("sortie.txt");
    BufferedWriter writer = new BufferedWriter(fw);
    
    writer.write("Première ligne\n");
    writer.write("Deuxième ligne");
    
    writer.close();
} catch (Exception e) {
    System.out.println("Erreur : " + e.getMessage());
}
```

- **Scanner** : Utile pour lire les entrées utilisateur depuis la console
- **BufferedReader** : Efficace pour lire des fichiers ligne par ligne
- **BufferedWriter** : Permet d'écrire dans un fichier avec un buffer
- **Important** : Toujours fermer les flux (close()) après utilisation
