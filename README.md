# DevTasks

Aplicació web senzilla de gestió de tasques desenvolupada amb HTML, CSS i JavaScript.

🌐 **Web publicada:** https://armanalidaw.github.io/PROJ1_Projecte_Intermodular/

## Descripcion
En devTasks puedes:
- Crear tareas
- Marcar como completado
- Eliminar tareas
- Filtrar como: Todos , Pendientes o completados
- Ver estadisticas como: tareas en total, tareas pendientes y tareas completados.
Las tareas se guardan en LocalStorage de navegador. asi que despues de recargar no se pierden las tasca creadas o modificadas

## Instal·lació
Deberia que tener instalado [Node.js](https://nodejs.org/)

```bash
git clone https://github.com/ArmanAliDaw/PROJ1_Projecte_Intermodular.git
cd PROJ1_Projecte_Intermodular
npm install
```

## Tests
Los tests estan en la carpeta `tests/`

```bash
npm test
```
Si todo sale en verde (✓), significa que el codigo funciona correctamente.

## GitHub Actions
Los workflows son automatizados y se ejecutan en GitHub. Estan es `.github/workflows/`.
**CI** (`ci.yml`) En cada push y en cada Pull Requests installa las dependencias y ejecuta los tests. Si algun test falla, le marca en rojo ❌.
**Depoly** (`deploy.yml`) Al hacer push a main se lo publica a github pages.

##Pull Requests

Nunca hay que trabaja directamente en `main`. El proceso es:
 
1. Crear una rama nueva.
2. Hacer los cambios y subirlos.
3. Hacer un Pull Request hacia `main`.
4. Los tests se ejecutan automacticamente.
5. Si los tests pasan ✅, se hace el merge.
6. Los cambios a llegar a `main`, se suben a la pagina tambien

## Deploy
Este es el enlace de la web publicada:
🔗 https://armanalidaw.github.io/PROJ1_Projecte_Intermodular/

## Dependencias
Las dependecias se instala con npm y estan gestionado por **Dependabot**:
- Dependabot revisa cada semana si hay versiones nuevas.
- Si las hay, abre una Pull Request automáticamente.
- Esa Pull Request pasa por los tests; si salen bien, se puede aceptar.

## Arquitectura 
```
proyecto/
├── index.html
├── css/style.css
├── js/
│   ├── app.js
│   └── testmanager.js
├── tests/
│   └── testmanager.test.js
└── package.json
```
La aplicacion javascript es dividio entre 2 fitxeros porque `js/app.js/` contiene document(DOM) que se ejecuta en navegador. y eso produce errores en los tests. por eso. los funciones esta separados en otro fitxero `js/testmanager.js`.

