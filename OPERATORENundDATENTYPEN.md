# Operatoren und Datentypen in JavaScript

Dieses Dokument gibt einen Überblick über die grundlegenden Datentypen und Operatoren in JavaScript und enthält Übungsaufgaben, um dein Verständnis zu vertiefen.

---

## 1. Datentypen

JavaScript unterscheidet zwischen primitiven Datentypen und Objekttypen.

### 1.1 Primitive Datentypen

* **Number**: Zahlentyp für Ganz- und Gleitkommazahlen (z. B. `42`, `3.14`).
* **String**: Zeichenkette in Anführungszeichen (z. B. `'Hallo'`, `"Welt"`).
* **Boolean**: Wahrheitswerte `true` und `false`.
* **Undefined**: Wert, wenn eine Variable deklariert, aber nicht initialisiert wurde.
* **Null**: Expliziter „leerer“ oder „nicht vorhandener“ Wert.
* **Symbol** (ES6): Einzigartige und unveränderliche Werte.
* **BigInt** (ES2020): Ganzzahlen grösser als `Number.MAX_SAFE_INTEGER`.

### 1.2 Objekttypen

* **Object**: Sammlung von Schlüssel-Wert-Paaren (z. B. `{ name: 'Max', age: 25 }`).
* **Array**: Geordnete Liste von Werten (z. B. `[1, 2, 3]`).
* **Function**: Spezialisierter Objekttyp für Funktionen.

### 1.3 Typüberprüfung

* `typeof`-Operator: Gibt als String den Datentyp eines Operanden zurück.

  ```js
  typeof 42;        // 'number'
  typeof 'Java';    // 'string'
  typeof true;      // 'boolean'
  typeof undefined; // 'undefined'
  typeof null;      // 'object' (historisch bedingt)
  ```
* `instanceof`: Prüft, ob ein Objekt von einer bestimmten Konstruktorfunktion abstammt.

  ```js
  [] instanceof Array;     // true
  {} instanceof Object;    // true
  ```

---

## 2. Operatoren

### 2.1 Arithmetische Operatoren

| Operator | Beschreibung      | Beispiel      |
| -------- | ----------------- | ------------- |
| `+`      | Addition          | `5 + 3 // 8`  |
| `-`      | Subtraktion       | `5 - 3 // 2`  |
| `*`      | Multiplikation    | `5 * 3 // 15` |
| `/`      | Division          | `10 / 2 // 5` |
| `%`      | Modulo (Restwert) | `10 % 3 // 1` |
| `**`     | Potenzierung      | `2 ** 3 // 8` |

### 2.2 Zuweisungsoperatoren

| Operator | Beschreibung                 | Beispiel              |
| -------- | ---------------------------- | --------------------- |
| `=`      | Einfache Zuweisung           | `x = 5`               |
| `+=`     | Addition und Zuweisung       | `x += 2 // x = x + 2` |
| `-=`     | Subtraktion und Zuweisung    | `x -= 2 // x = x - 2` |
| `*=`     | Multiplikation und Zuweisung | `x *= 2 // x = x * 2` |
| `/=`     | Division und Zuweisung       | `x /= 2 // x = x / 2` |
| `%=`     | Modulo und Zuweisung         | `x %= 2 // x = x % 2` |

### 2.3 Vergleichsoperatoren

| Operator | Beschreibung                         | Beispiel             |
| -------- | ------------------------------------ | -------------------- |
| `==`     | Gleich (nach Typumwandlung)          | `5 == '5' // true`   |
| `===`    | Streng gleich (kein Type Coercion)   | `5 === '5' // false` |
| `!=`     | Ungleich (nach Typumwandlung)        | `5 != '5' // false`  |
| `!==`    | Streng ungleich (kein Type Coercion) | `5 !== '5' // true`  |
| `<`      | Kleiner als                          | `3 < 5 // true`      |
| `<=`     | Kleiner gleich                       | `3 <= 3 // true`     |
| `>`      | Grösser als                           | `5 > 3 // true`      |
| `>=`     | Grösser gleich                        | `5 >= 5 // true`     |

### 2.4 Logische Operatoren

| Operator | Beschreibung      | Beispiel                 |                  |        |   |                 |
| -------- | ----------------- | ------------------------ | ---------------- | ------ | - | --------------- |
| `&&`     | Logisches „Und“   | `true && false // false` |                  |        |   |                 |
| \`       |                   | \`                       | Logisches „Oder“ | \`true |   | false // true\` |
| `!`      | Logisches „Nicht“ | `!true // false`         |                  |        |   |                 |

### 2.5 Sonstige Operatoren

* **Ternärer Operator**: Kurzform für eine `if`-Abfrage.

  ```js
  const status = age >= 18 ? 'volljährig' : 'minderjährig';
  ```
* **Komma-Operator**: Führt mehrere Ausdrücke aus und liefert den letzten Wert.

  ```js
  let a = (1, 2, 3); // a ist 3
  ```
* **Spread-Operator (`...`)**: Zerlegt Arrays/Objekte oder fügt sie zusammen.

  ```js
  const arr1 = [1, 2];
  const arr2 = [...arr1, 3]; // [1,2,3]
  ```

---
