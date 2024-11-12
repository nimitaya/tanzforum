# Tailwind
[Installation](https://tailwindcss.com/docs/installation)
[Utility-First Fundamentals](https://tailwindcss.com/docs/utility-first)
[Cheatsheet für Tailwind](https://tailwindcomponents.com/cheatsheet/)

## Hier sind die Schritte, um Tailwind CSS in einem HTML-Projekt einzurichten:

1. Erstelle dein `index.html`-Datei wie gewohnt.
2. Erstelle ein `style.css`-Datei und verlinke sie in deinem `index.html`-Dokument. (wird auch output.css in Documentation genannt)
   ```html
   <link rel="stylesheet" href="style.css" />
   ```
3. Erstelle eine `tailwind.css`-Datei. (wird auch input.css in Documentation genannt)
4. Füge die folgenden Zeilen im VSCode `Terminal` ein:
   ```bash
   npm init -y
   npm install -D tailwindcss
   npx tailwindcss init
   ```
   - `npm init -y` erstellt eine `package.json`-Datei. **(Optional) - Du kannst diese Datei öffnen und `name`, `version`** (von dieser Anwendung), **`description`, `author`, etc. ändern.**
        - `-y` ist dafür da, damit wir alles mit "Yes" beantworten
        - das nutzen ist ordentlicher
   - `npm install -D tailwindcss` installiert Tailwind CSS.
        - `-D` ist damit nur für dev-dependency
   - `npx tailwindcss init` erstellt eine `tailwind.config.js`-Datei.

5. Offne die `tailwind.config.js`-Datei und ersetze die Zeile `content: []` mit:
   ```js
   content: ["./**/*.html"],
   ```
   - Diese Zeile sagt Tailwind CSS, dass es alle HTML- ( `.{html, js}` und JS-Dateien) im Projekt durchsuchen soll.

6. Füge die folgenden Zeilen in deiner `tailwind.css`-Datei (oder input) ein:
   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;
   ```

7. Füge die folgenden Zeilen in deiner `package.json`-Datei im `scripts`-Abschnitt ein:
   ```json
     "dev": "npx tailwindcss -i ./tailwind.css -o ./style.css --watch"
   ```
   - Diese Zeilen sagen Tailwind CSS, dass es die `tailwind.css`-Datei in die `style.css`-Datei kompilieren soll.
      - `-o` mach Output in `./style.css`
   - mit `npm run` und dem Namen, hier `dev` wird dieses Script ausgeführt

8. Führe den folgenden Befehl im `Terminal` aus:
   ```bash
    npm run dev
   ```
9. Füge ein Testelement in deinem `index.html`-Dokument ein:
```html
<div class="bg-rose-900 text-white p-4">Hello World!</div>
```

11. Öffne dein `index.html`-Dokument im Browser (mit dem `Live Server`-Plugin, wenn du möchtest) und überprüfe, ob das Testelement korrekt angezeigt wird.

12. Erstelle eine `.gitignore`-Datei und füge die folgenden Zeilen ein:
    ```
    node_modules

    package-lock.json
    ```

- wenn man runterlädt, dann mit `npm i` oder so dann erstellt lokal node_modules und packages-lock.json
- muss man also nicht hochladen

13. VSCode Extensions
- Installiere die [Tailwind CSS IntelliSense](https://tailwindcss.com/docs/editor-setup) Extension
- [Prettier Plugin](https://github.com/tailwindlabs/prettier-plugin-tailwindcss) für Reihenfolge der Klasse