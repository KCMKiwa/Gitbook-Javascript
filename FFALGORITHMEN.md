# JavaScript Algorithmen

Willkommen zu diesem GitBook-Kapitel über Algorithmen in JavaScript. Dieses Dokument bietet dir eine solide Grundlage, um die wichtigsten algorithmischen Konzepte zu verstehen und sie mit JavaScript umzusetzen.

## Inhalt

* [Einleitung in Algorithmen](#1-einleitung-in-algorithmen)
* [Sortieralgorithmen](#2-sortieralgorithmen)

  * [Bubble Sort](#bubble-sort)
  * [Selection Sort](#selection-sort)
  * [Insertion Sort](#insertion-sort)
  * [Merge Sort](#merge-sort)
  * [Quick Sort](#quick-sort)
* [Suchalgorithmen](#3-suchalgorithmen)

  * [Lineare Suche](#lineare-suche)
  * [Binäre Suche](#binäre-suche)
* [Rekursion](#4-rekursion)
* [Backtracking](#5-backtracking)
* [Dynamische Programmierung](#6-dynamische-programmierung)
* [Graphenalgorithmen](#7-graphenalgorithmen)

  * [Tiefensuche (DFS)](#tiefensuche-dfs)
  * [Breitensuche (BFS)](#breitensuche-bfs)
* [Zeit- und Speicherkomplexität](#8-zeit--und-speicherkomplexität)

---

## 1. Einleitung in Algorithmen

Ein Algorithmus ist eine Schritt-für-Schritt-Anleitung zur Lösung eines Problems. In JavaScript lassen sich viele Algorithmen direkt mit Arrays, Objekten und Funktionen umsetzen.

## 2. Sortieralgorithmen

### Bubble Sort

```js
function bubbleSort(arr) {
  let n = arr.length;
  for (let i = 0; i < n - 1; i++) {
    for (let j = 0; j < n - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]];
      }
    }
  }
  return arr;
}
```

### Selection Sort

```js
function selectionSort(arr) {
  for (let i = 0; i < arr.length; i++) {
    let min = i;
    for (let j = i + 1; j < arr.length; j++) {
      if (arr[j] < arr[min]) min = j;
    }
    [arr[i], arr[min]] = [arr[min], arr[i]];
  }
  return arr;
}
```

### Insertion Sort

```js
function insertionSort(arr) {
  for (let i = 1; i < arr.length; i++) {
    let key = arr[i];
    let j = i - 1;
    while (j >= 0 && arr[j] > key) {
      arr[j + 1] = arr[j];
      j = j - 1;
    }
    arr[j + 1] = key;
  }
  return arr;
}
```

### Merge Sort

```js
function mergeSort(arr) {
  if (arr.length <= 1) return arr;
  const mid = Math.floor(arr.length / 2);
  const left = mergeSort(arr.slice(0, mid));
  const right = mergeSort(arr.slice(mid));

  return merge(left, right);
}

function merge(left, right) {
  const result = [];
  while (left.length && right.length) {
    result.push(left[0] < right[0] ? left.shift() : right.shift());
  }
  return result.concat(left, right);
}
```

### Quick Sort

```js
function quickSort(arr) {
  if (arr.length <= 1) return arr;
  const pivot = arr[arr.length - 1];
  const left = [];
  const right = [];
  for (let i = 0; i < arr.length - 1; i++) {
    if (arr[i] < pivot) left.push(arr[i]);
    else right.push(arr[i]);
  }
  return [...quickSort(left), pivot, ...quickSort(right)];
}
```

## 3. Suchalgorithmen

### Lineare Suche

```js
function linearSearch(arr, target) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === target) return i;
  }
  return -1;
}
```

### Binäre Suche (vorausgesetzt: sortiertes Array)

```js
function binarySearch(arr, target) {
  let left = 0, right = arr.length - 1;
  while (left <= right) {
    const mid = Math.floor((left + right) / 2);
    if (arr[mid] === target) return mid;
    else if (arr[mid] < target) left = mid + 1;
    else right = mid - 1;
  }
  return -1;
}
```

## 4. Rekursion

Rekursion ist ein Prinzip, bei dem eine Funktion sich selbst aufruft.

### Beispiel: Fakultät

```js
function factorial(n) {
  if (n <= 1) return 1;
  return n * factorial(n - 1);
}
```

## 5. Backtracking

### Beispiel: N-Queens Problem (vereinfachtes Beispiel)

```js
function solveNQueens(n) {
  const result = [];
  const board = Array(n).fill().map(() => Array(n).fill('.'));

  function isSafe(row, col) {
    for (let i = 0; i < row; i++) {
      if (board[i][col] === 'Q') return false;
      if (col - (row - i) >= 0 && board[i][col - (row - i)] === 'Q') return false;
      if (col + (row - i) < n && board[i][col + (row - i)] === 'Q') return false;
    }
    return true;
  }

  function place(row) {
    if (row === n) {
      result.push(board.map(r => r.join('')));
      return;
    }
    for (let col = 0; col < n; col++) {
      if (isSafe(row, col)) {
        board[row][col] = 'Q';
        place(row + 1);
        board[row][col] = '.';
      }
    }
  }

  place(0);
  return result;
}
```

## 6. Dynamische Programmierung

### Beispiel: Fibonacci mit Memoization

```js
function fibonacci(n, memo = {}) {
  if (n <= 1) return n;
  if (memo[n]) return memo[n];
  memo[n] = fibonacci(n - 1, memo) + fibonacci(n - 2, memo);
  return memo[n];
}
```

## 7. Graphenalgorithmen

### Tiefensuche (DFS)

```js
function dfs(graph, start, visited = new Set()) {
  if (visited.has(start)) return;
  visited.add(start);
  console.log(start);
  for (const neighbor of graph[start]) {
    dfs(graph, neighbor, visited);
  }
}
```

### Breitensuche (BFS)

```js
function bfs(graph, start) {
  const queue = [start];
  const visited = new Set();

  while (queue.length) {
    const node = queue.shift();
    if (!visited.has(node)) {
      console.log(node);
      visited.add(node);
      queue.push(...graph[node]);
    }
  }
}
```

## 8. Zeit- und Speicherkomplexität

Algorithmen werden häufig in **Big-O Notation** beschrieben:

| Notation   | Bedeutung              |
| ---------- | ---------------------- |
| O(1)       | konstant               |
| O(log n)   | logarithmisch          |
| O(n)       | linear                 |
| O(n log n) | effizient (Sortierung) |
| O(n^2)     | quadratisch            |

---

## Weiterführende Ressourcen

* [JavaScript.info](https://javascript.info/)
* [MDN Web Docs](https://developer.mozilla.org/de/)
* [Visualgo.net](https://visualgo.net/en)
