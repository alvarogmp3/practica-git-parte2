## Ejercicio 1. Ciclo básico de Git
**Archivo trabajado:** notas.md  
**Comandos usados:**
git add notas.md
git commit -m "feat: añade notas iniciales"
git push origin main
git commit -am "feat: amplía notas.md"
git push origin main

**Explicación:**  
Se creó el archivo notas.md con un listado de asignaturas. git add y git commit registran los cambios localmente. git push sube los commits al repositorio remoto. La opción -am permite hacer commit directo de los archivos modificados.

---

## Ejercicio 2. Ramas
**Archivo trabajado:** notas.md  
**Comandos usados:**
git checkout -b feature-tareas
git commit -am "feat: añade lista de tareas pendientes"
git push -u origin feature-tareas
git checkout main
git merge feature-tareas
git push origin main
git branch -d feature-tareas
git push origin --delete feature-tareas

**Explicación:**  
Se creó una rama para añadir tareas pendientes. Se fusionó con main usando merge. Las ramas locales y remotas se borraron para mantener limpio el repositorio.

---

## Ejercicio 3. Borrado y restauración
**Archivo trabajado:** temporal.txt  
**Comandos usados:**
git rm temporal.txt
git commit -m "chore: elimina archivo temporal"
git push origin main
git restore --source HEAD~1 temporal.txt

**Explicación:**  
Se eliminó el archivo temporal.txt del repositorio y del directorio. Se restauró desde el commit anterior usando git restore.

---

## Ejercicio 4. Logs y diffs
**Archivo trabajado:** notas.md  
**Comandos usados:**
git log --oneline --graph --all
git diff HEAD~1 HEAD

**Explicación:**  
git log --oneline --graph --all muestra un historial resumido y gráfico de todos los commits y ramas. git diff HEAD~1 HEAD muestra los cambios entre los dos últimos commits, indicando qué líneas fueron añadidas o eliminadas.

---

## Ejercicio 5. Conflictos intencionados
**Archivos trabajados:** notas.md, conflicto.md  
**Comandos usados:**
git merge feature-conflicto
git add notas.md
git commit -m "fix: resuelve conflicto de Organizar apuntes"
git push origin main
git add conflicto.md
git commit -m "docs: explica resolución del conflicto"
git push origin main

**Explicación:**  
Se resolvió un conflicto manual en notas.md donde la misma línea se modificó en main y feature-conflicto. conflicto.md documenta cómo se resolvió, combinando la tarea “Organizar apuntes” en una sola línea.

---

## Ejercicio 6. Tags
**Comandos usados:**
git tag v1.0
git push origin --tags
git tag -a v1.1 -m "Primera versión estable"
git push origin --tags

**Explicación:**  
v1.0 es un tag ligero que apunta a un commit específico. v1.1 es un tag anotado con mensaje, útil para marcar versiones estables. git push --tags sube todos los tags al repositorio remoto.
