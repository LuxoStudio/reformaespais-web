# REFORMA ESPAIS — MANUAL DEL PROYECTO

## Proyecto

Esta es la web oficial de Reforma Espais.

Tecnología:
- Astro
- HTML
- CSS
- JavaScript cuando sea necesario

Repositorio de producción:
LuxoStudio/reformaespais-web

Dominio oficial:
https://reformaespais.es

También funciona:
https://www.reformaespais.es


## IMPORTANTE — REPOSITORIOS

El repositorio actual y de producción es:

LuxoStudio/reformaespais-web

Existe un repositorio antiguo:

LuxoStudio/Reformaespais

NO utilizar ni modificar el repositorio antiguo para la web actual.


## PRODUCCIÓN

La web se publica mediante:

VS Code
↓
Git
↓
GitHub
↓
GitHub Actions
↓
GitHub Pages
↓
reformaespais.es

GitHub Pages utiliza como fuente:

GitHub Actions

NO cambiar la fuente a "Deploy from a branch".


## DOMINIO Y DNS

El dominio reformaespais.es está gestionado en OVH.

Los registros DNS actuales son:

@ A 185.199.108.153
@ A 185.199.109.153
@ A 185.199.110.153
@ A 185.199.111.153

www CNAME luxostudio.github.io.

NO eliminar ni modificar estos registros sin comprobar primero el motivo.


## ESTRUCTURA PRINCIPAL

El proyecto utiliza:

src/
├── components/
├── layouts/
├── pages/
└── styles/

public/
└── branding/
└── projects/
└── images/

Las páginas actuales son:

/
 
/reformas-integrales/

/cocinas/

/banos/

/interiorismo/


## COMPONENTES

Los componentes principales están en:

src/components/

Entre ellos:

- Navbar.astro
- Contact.astro
- Footer.astro
- cta.astro

IMPORTANTE:

El archivo CTA se llama:

cta.astro

con "cta" en minúsculas.

Por tanto los imports deben utilizar:

import CTA from "../components/cta.astro";

GitHub Actions funciona sobre Linux y distingue entre mayúsculas y minúsculas.

No utilizar:

import CTA from "../components/CTA.astro";


## LOGO

El logo utilizado actualmente está en:

public/branding/logo-reformaespais.png

No sustituir el logo por imágenes generadas o capturas.


## DESARROLLO LOCAL

Para iniciar el servidor de desarrollo se puede utilizar:

astro dev --background

Para comprobar el servidor:

astro dev status

Para detenerlo:

astro dev stop

Para consultar los logs:

astro dev logs

También se puede utilizar el flujo habitual de npm si está configurado en package.json.


## COMPROBAR EL PROYECTO

Antes de publicar cambios importantes ejecutar:

npm run build

El resultado correcto debe terminar con:

[build] Complete!

Actualmente el proyecto genera 5 páginas:

/
/banos/
/cocinas/
/interiorismo/
/reformas-integrales/


## PUBLICAR CAMBIOS

Después de modificar la web:

1. Comprobar visualmente los cambios.
2. Ejecutar:

npm run build

3. Si el build funciona correctamente:

git add .

4. Crear el commit:

git commit -m "Descripción del cambio"

5. Subirlo:

git push

Después del push, GitHub Actions compilará y publicará automáticamente la web.


## SI GITHUB ACTIONS FALLA

NO hacer cambios aleatorios.

Primero:

1. Entrar en GitHub.
2. Abrir el repositorio:
   LuxoStudio/reformaespais-web
3. Entrar en Actions.
4. Abrir la ejecución que aparece en rojo.
5. Entrar en Build.
6. Buscar el primer error real.
7. Corregir únicamente ese problema.
8. Ejecutar npm run build localmente.
9. Comprobar que aparece:

[build] Complete!

10. Hacer commit y push.


## ERROR IMPORTANTE YA RESUELTO

Durante el primer despliegue GitHub falló porque Astro necesita una versión moderna de Node.

El workflow utiliza actualmente:

Node.js 22

No volver a cambiarlo a Node 20.


## GITHUB ACTIONS

El workflow de producción está en:

.github/workflows/deploy.yml

Este workflow:

1. Descarga el repositorio.
2. Instala Node.
3. Instala dependencias.
4. Ejecuta npm run build.
5. Genera dist/.
6. Sube dist como artifact.
7. Publica el artifact en GitHub Pages.


## DISEÑO

La web actual se considera la versión estable.

No rediseñar secciones existentes sin que el usuario lo solicite.

Mantener:

- estética limpia y premium
- colores neutros
- verde de marca
- buena separación entre bloques
- tipografía clara
- diseño responsive
- navegación móvil
- botones de contacto hacia WhatsApp


## CAMBIOS FUTUROS

Cuando el usuario quiera modificar una sección:

1. Identificar primero el archivo correspondiente.
2. Revisar el código existente.
3. No modificar partes que no estén relacionadas.
4. Hacer cambios pequeños y controlados.
5. Ejecutar npm run build.
6. Comprobar visualmente.
7. Hacer commit y push solamente cuando todo funcione.


## REGLA PRINCIPAL

La web de reformaespais.es está actualmente funcionando correctamente.

NO volver a configurar desde cero:

- OVH
- DNS
- GitHub Pages
- GitHub Actions
- dominio personalizado

salvo que exista un problema real.

Antes de cambiar cualquiera de estas configuraciones, comprobar primero el estado actual.


## DOCUMENTACIÓN DE ASTRO

Documentación oficial:

https://docs.astro.build

Para tareas relacionadas con Astro consultar:

- Routing:
  https://docs.astro.build/en/guides/routing/

- Astro components:
  https://docs.astro.build/en/basics/astro-components/

- Styling:
  https://docs.astro.build/en/guides/styling/

- Content collections:
  https://docs.astro.build/en/guides/content-collections/

- Framework components:
  https://docs.astro.build/en/guides/framework-components/

- Internationalization:
  https://docs.astro.build/en/guides/internationalization/


## CONTINUAR EN UN CHAT NUEVO

Si se abre un chat nuevo para continuar trabajando en Reforma Espais:

1. Leer este archivo AGENTS.md.
2. Utilizar la configuración descrita aquí.
3. No volver a configurar el dominio ni GitHub Pages si ya funcionan.
4. Preguntar qué modificación quiere realizar el usuario.
5. Guiar al usuario paso a paso cuando tenga que utilizar VS Code, GitHub o el terminal.