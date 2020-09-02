### Разворачивание
Установка `npm install electron --save-dev`

Структура
```
your-app/
├── package.json
├── main.js
└── index.html
```

package.json++:
```
  "main": "main.js",
  "scripts": {
    "start": "electron ."
  },
```

Минимальный main.js для запуска, index.html можно и пустым оставить
```
const { app, BrowserWindow } = require('electron')

function createWindow () {
  // Create the browser window.
  const win = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences: {
      nodeIntegration: true
    }
  })

  // and load the index.html of the app.
  win.loadFile('index.html')
}

app.whenReady().then(createWindow)
```

### Сборка

Установка [electron-builder](https://github.com/electron-userland/electron-builder) 
`npm install electron-builder --save-dev`

package.json++:
```
  "scripts": {
    ...
    "pack": "electron-builder --dir", # сборка в папку
    "dist": "electron-builder" # собрать билд
  },
```
### Тестоирование

Установка [mocha](https://mochajs.org/) 
`npm install mocha --save-dev`

package.json++:
```
  "scripts": {
    ...
    "test": "mocha",
  },
```

