# 🚀 Publicar en GitHub Pages - Guía paso a paso

## Requisitos previos

1. **Cuenta de GitHub** - Crea una en https://github.com si no tienes
2. **Git instalado** - Descarga desde https://git-scm.com/download/win
3. **Tu carpeta Faenamiento** con los archivos

---

## PASO 1: Verificar que Git funciona

Abre PowerShell o CMD y ejecuta:

```powershell
git --version
```

Deberías ver algo como: `git version 2.40.0.windows.1`

---

## PASO 2: Navegar a la carpeta del proyecto

```powershell
cd "C:\Users\Usuario\Desktop\Faenamiento"
```

Verifica que ves los archivos:
```powershell
dir
```

Deberías ver:
- `index.html` ✓
- `README.md` ✓
- `.gitignore` ✓

---

## PASO 3: Inicializar repositorio local

```powershell
git init
```

Luego configura tu email y nombre (importante para GitHub):

```powershell
git config user.email "roggeras19@gmail.com"
git config user.name "Rogger"
```

O globalmente (para todos los repos):

```powershell
git config --global user.email "roggeras19@gmail.com"
git config --global user.name "Rogger"
```

---

## PASO 4: Agregar archivos al repositorio

```powershell
git add .
```

Verifica qué se agregó:
```powershell
git status
```

Deberías ver los 3 archivos en verde (staged).

---

## PASO 5: Hacer el primer commit

```powershell
git commit -m "Initial commit: Dashboard Faenamiento Porcino v41"
```

---

## PASO 6: Crear repositorio en GitHub

1. Ve a https://github.com/new
2. **Repository name**: `faenamiento` (sin mayúsculas)
3. **Description**: "Dashboard interactivo de monitoreo de faenamiento porcino"
4. **Visibility**: Elige "Public" (para GitHub Pages)
5. NO marques "Initialize with README" (ya lo tenemos)
6. Haz clic en **Create repository**

---

## PASO 7: Conectar repositorio local a GitHub

GitHub te mostrará comandos. En PowerShell, ejecuta:

```powershell
git remote add origin https://github.com/TU-USUARIO/faenamiento.git
git branch -M main
git push -u origin main
```

**IMPORTANTE**: Reemplaza `TU-USUARIO` con tu nombre de usuario de GitHub

Ejemplo:
```powershell
git remote add origin https://github.com/rogger/faenamiento.git
git branch -M main
git push -u origin main
```

Se te pedirá autenticación:
- Si ves un navegador: inicia sesión en GitHub
- Si pide usuario/contraseña: usa tu email de GitHub + Personal Access Token (PAT)
  
  ℹ️ Para crear un PAT: https://github.com/settings/tokens

---

## PASO 8: Activar GitHub Pages

1. Ve a tu repositorio: https://github.com/TU-USUARIO/faenamiento
2. Haz clic en **Settings** (arriba)
3. En el menú izquierdo, busca **Pages** (bajo "Code and automation")
4. En **Source**, selecciona:
   - Branch: `main`
   - Folder: `/ (root)`
5. Haz clic en **Save**

GitHub procesará durante 1-2 minutos...

---

## PASO 9: ¡Listo!

Tu sitio estará disponible en:

```
https://TU-USUARIO.github.io/faenamiento/
```

Ejemplo:
```
https://rogger.github.io/faenamiento/
```

---

## Actualizar el dashboard en el futuro

Cada vez que cambies `index.html`:

```powershell
cd "C:\Users\Usuario\Desktop\Faenamiento"
git add index.html
git commit -m "Update: descripción del cambio"
git push origin main
```

En 1-2 minutos el cambio estará en línea. ¡Sin necesidad de re-publicar!

---

## Si algo falla...

### Error: "Authentication failed"

```powershell
git config --global credential.helper wincred
```

Luego intenta `git push` de nuevo y usa tu PAT.

### Error: "fatal: not a git repository"

Asegúrate de estar en la carpeta correcta:
```powershell
cd "C:\Users\Usuario\Desktop\Faenamiento"
pwd
```

### El sitio no aparece

- Espera 2-3 minutos después de activar Pages
- Recarga la página varias veces (Ctrl+Shift+R)
- Verifica que la rama sea `main` (no `master`)
- Chequea que `index.html` esté en la raíz, no en una subcarpeta

---

## Compartir con tu gerencia

Una vez publicado, comparte el enlace:

```
📊 Dashboard en vivo:
https://rogger.github.io/faenamiento/

Datos se actualizan automáticamente cada vez que abres el enlace.
Sin necesidad de descargar archivos ni login.
```

---

## Resumen de comandos (cheat sheet)

```powershell
# Primera vez
cd "C:\Users\Usuario\Desktop\Faenamiento"
git init
git config user.email "roggeras19@gmail.com"
git config user.name "Rogger"
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/rogger/faenamiento.git
git branch -M main
git push -u origin main

# Actualizaciones futuras
git add index.html
git commit -m "Descripción del cambio"
git push origin main
```

---

¡Éxito! 🚀

Para preguntas: https://docs.github.com/en/pages
