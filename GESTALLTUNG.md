# Styling und DOM-Manipulation in JavaScript

Dieses Dokument erläutert Techniken, um das Aussehen deiner Webanwendung dynamisch über JavaScript zu steuern.

---

## 1. Inline-Styles mit `style`

* Über das `style`-Objekt können einzelne CSS-Eigenschaften gesetzt werden:

  ```js
  const element = document.getElementById('test');
  element.style.backgroundColor = 'blue';
  element.style.fontSize = '2rem';
  ```

## 2. Klassenmanagement mit `classList`

* Klassen hinzufügen, entfernen und toggeln:

  ```js
  const element = document.getElementById('testIdTwo');
  element.classList.add('active');
  element.classList.remove('hidden');
  element.classList.toggle('visible');
  ```

## 3. CSS-Variablen dynamisch ändern

* Zugriff und Änderung von CSS-Variablen (Custom Properties):

  ```js
  document.documentElement.style.setProperty('--primary-color', '#ff6347');
  ```

## 4. Erstellen und Einfügen von Stylesheets

* Ein neues Stylesheet im `<head>`-Bereich erstellen und einfügen:

  ```js
  const style = document.createElement('style');
  style.textContent = `
    .new-class {
      color: purple;
      margin: 10px;
    }
  `;
  document.head.append(style);
  ```

*Diese Techniken helfen dir, das Aussehen deiner Webanwendung dynamisch zu steuern.*
