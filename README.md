# Integración de métricas ágiles: Burn-Down y lead time con scripts personalizado

Este repositorio contiene todas las contribuciones realizadas por mi en el proyecto. Para verlo completo dirigirse al **Repositorio Grupal**:

- https://github.com/JunalChowdhuryG/Grupo-2-Practica-Calificada-3/tree/feature-generar-kanban

Nombre: **Zapata Inga, Janio Adolfo**

## Contribuciones

Cada feature de la que me encargé fue trabajada en su rama correspondiente (ej `feat-xxxx`). Luego de realizar los commits correspondientes y hacerle push, cree un pull-request solicitando un merge hacia la rama `develop`. Las evidencias se encuentran en la carpeta `branches/Sprintx`.

### Sprint 1

- **Issue 2**: Implementar hook commit-msg

  ````bash
        #!/bin/bash
        #Hook para asegurar un correcto mensaje de commit usando prefijos estandar

        # leer el mensaje del commit
        MSJ_COMMIT=$1
        MENSAJE=$(cat "$MSJ_COMMIT")

        # solo se permiten tipos feat, fix, refactor, docs, test
        PATRON="^(feat|fix|refactor|docs|test)\[#([0-9]+)\]: .+"

        if ! echo "$MENSAJE" | grep -Eq "$PATRON"; then
            echo " Error: El mensaje del commit debe seguir el patron '<tipo>[#n]: mensaje'"
            echo " Tipos permitidos: feat, fix, refactor, docs, test"
            echo " Ejemplo valido: feat[#1]: Inicializar repositorio y estructura"
            exit 1
        fi

        exit

      ```

  ````

  Este hook recibe como parámetro el mensaje del commit. Luego lo compara con un patrón

  - `^(feat|fix|refactor|docs|test)` : Que comienza con cualquiera de los prefijos dentro del paréntesis
  - `\[`: Backslash para que reconozca el caracter `[`y no lo interprete como especial.
  - `([0-9]+)`: Caracteres numéricos, de una a más cifras
  - `\]:`: Cerrando `]`y `:`
  - `.+`: El `.`representa cualquier caracter y el `+`que puedan haber una o más incidencias. (Cualquier conjunto de caracteres de cualquier longitud)

- **Issue 13**: Agregar documentación del sprint 1

### Sprint 2

### Sprint 3
