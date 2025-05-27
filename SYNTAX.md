# Syntax

JavaScript-Syntax beschreibt die Regeln, wie JavaScript-Programme geschrieben werden. Hier sind einige grundlegende Bestandteile:

## 📦 Variablendeklaration

```javascript
let name = "Max";       // veränderlich, Block-Scope
const alter = 25;        // konstant, Block-Scope
var beruf = "Entwickler"; // veränderlich, Funktions-Scope (veraltet)
```

## 🧠 Funktionen

```javascript
function begruessung(name) {
    return "Hallo, " + name + "!";
}

// Arrow Function
const begruessungNeu = (name) => `Hallo, ${name}!`;
```

## 🔀 Bedingungen

```javascript
if (alter > 18) {
    console.log("Volljährig");
} else if (alter === 18) {
    console.log("Genau 18 Jahre alt");
} else {
    console.log("Minderjährig");
}

// Ternärer Operator
const status = alter >= 18 ? "Erwachsen" : "Kind";
```

## 🔁 Schleifen

```javascript
// for-Schleife
for (let i = 0; i < 5; i++) {
    console.log(i);
}

// while-Schleife
let count = 0;
while (count < 5) {
    console.log(count);
    count++;
}

// for...of (für Arrays)
const farben = ["rot", "grün", "blau"];
for (const farbe of farben) {
    console.log(farbe);
}
```

## 📦 Objekte und Arrays

```javascript
const person = {
    name: "Max",
    alter: 25,
    beruf: "Entwickler"
};

console.log(person.name);

const zahlen = [1, 2, 3, 4];
console.log(zahlen[0]);
```

## 📌 Weitere Themen

* `switch`-Anweisungen
* Template Literals (`` `Hallo ${name}` ``)
* Nullish Coalescing (`??`)
* Optional Chaining (`?.`)
* `try...catch` Fehlerbehandlung

---

Dieses Kapitel bietet einen Überblick über die Grundsyntax von JavaScript. Ideal zum schnellen Nachschlagen und für Einsteiger zum Lernen.
