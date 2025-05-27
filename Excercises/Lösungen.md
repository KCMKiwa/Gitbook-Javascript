# JavaScript Lösungen zu den Übungsaufgaben

Hier findest du die Lösungen zu den Aufgaben im Kapitel **JavaScript Übungsaufgaben**. Nutze sie zum Vergleichen und Lernen.

---

## 🔤 Grundlagen: Variablen & Datentypen

### Aufgabe 1

```javascript
let name = "Max";
console.log("Hallo, " + name + "!");
```

### Aufgabe 2

```javascript
let a = 7;
let b = 3;
console.log("Summe:", a + b);
console.log("Differenz:", a - b);
console.log("Produkt:", a * b);
console.log("Quotient:", a / b);
```

---

## 🧠 Funktionen

### Aufgabe 3

```javascript
function quadrat(x) {
  return x * x;
}
```

### Aufgabe 4

```javascript
function begruesse(name) {
  return `Hallo, ${name}!`;
}
```

---

## 🔁 Bedingungen und Schleifen

### Aufgabe 5

```javascript
function istVolljaehrig(alter) {
  return alter >= 18;
}
```

### Aufgabe 6

```javascript
for (let i = 1; i <= 10; i++) {
  console.log(i);
}
```

---

## 📚 Arrays und Objekte

### Aufgabe 7

```javascript
const farben = ["rot", "grün", "blau"];
for (let farbe of farben) {
  console.log(farbe);
}
```

### Aufgabe 8

```javascript
const person = {
  name: "Max",
  alter: 25,
  beruf: "Entwickler"
};
console.log(person.name);
console.log(person.alter);
console.log(person.beruf);
```

---

## ⚙️ Fortgeschritten: Rekursion & Suche

### Aufgabe 9

```javascript
function fakultaet(n) {
  if (n <= 1) return 1;
  return n * fakultaet(n - 1);
}
```

### Aufgabe 10

```javascript
function findeZahl(arr, zahl) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === zahl) return true;
  }
  return false;
}
```

---

Glückwunsch, wenn du alle Aufgaben gelöst hast! 🎉 Nutze diese Lösungen zum Verstehen und als Inspiration für eigene Varianten.
