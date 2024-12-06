# Tienda Sena

## Semantica del versionamiento

Nosotros usamos [Semantica de versionamiento](https://semver.org/) para nuestro proyecto. El numero de version esta basado en Mayor(X), Menor(Y), Path(Z).

## Version Mayor(X)
● Se incrementa solamente cuando se introducen cambios incompatibles con la versión anterior del API público. 
● Este cambio puede incluir modificaciones a nivel de versiones menores y de parches. 
● Al incrementar la versión mayor, las versiones menores y parche deben reiniciarse a 0.

## Version Menor(Y)
● Se incrementa cuando se introduce funcionalidad nueva compatible con la versión anterior del API público. 
● También se incrementa al añadir cualquier funcionalidad al API público o al mejorar el código privado. 
● Puede incluir cambios a nivel de parches. 
● Al incrementar la versión menor, la versión parche debe reiniciarse a 0. 

## Version Path o Parche(Z)
● Se incrementa solamente cuando se introducen correcciones de errores compatibles con versiones anteriores. 
● Una corrección de error se define como un cambio interno que corrige un comportamiento incorrecto. 

## Que implica cada tipo de cambio

## Version Mayor(X)
● Un ejemplo de cambio que amerita un incremento en la versión mayor sería la eliminación de una función del API o un cambio en el tipo de datos de un parámetro. 
●Cambiar el tipo de dato de un parámetro en una función del API. 
●Renombrar una función o clase del API. 
●Cambiar la estructura de datos fundamental del API. 

## Version Menor(Y)
● Un ejemplo de cambio que justifica un incremento en la versión menor sería la adición de una nueva función al API. 
● Extender una clase existente del API con nuevas funcionalidades. 
● Implementar una nueva característica que no afecte al API público, como una optimización del rendimiento. 

## Version Path o Parche(Z)
● Un ejemplo de cambio que corresponde a un incremento en la versión parche sería la corrección de un error que provocaba un fallo en una función. 
● Solucionar un problema de rendimiento en una parte del código que no afecta al API. 
● Mejorar la documentación sin modificar la funcionalidad del software. 

## Etiquetas pre-lanzamiento

● 1.0.0-TS-alpha: Versión alfa, generalmente la primera fase de prueba, con la posibilidad de cambios significativos. 
● 1.0.0-TS-alpha.1: Segunda versión alfa, indicando un progreso incremental desde la primera versión alfa. 
● 1.0.0-TS-beta: Versión beta, más estable que alfa, con la mayoría de las características implementadas, pero aún en pruebas. 
● 1.0.0-TS-beta.2: Segunda versión beta, con correcciones de errores y mejoras desde la primera beta. 
● 1.0.0-TS-rc.1: Primera versión candidata a lanzamiento (release candidate), considerada casi lista para la versión final, a menos que se encuentren errores críticos. 

Estas etiquetas indican el estado de desarrollo del software antes del lanzamiento estable. 

## Automatizar el versionamiento

# Git Tags: Marca versiones en Git. 

git tag -a v1.0.0 -m "Primera versión estable" 
git push origin v1.0.0 

# Herramientas como semantic-release: 
# Analizan los commits para determinar automáticamente la próxima versión. 
# Generan changelogs y publican la nueva versión.

Crear un Tag 
# Antes del lanzamiento se tendrán en cuenta las etiquetas 
# Se puede crear un tag anotado en Git utilizando el siguiente comando. Un tag anotado incluye un mensaje de descripción y otros metadatos como el nombre del creador y la fecha: 

sh 
● git tag -a v1.0.0

Ejemplo: 

● -a v1.0.0: La opción -a crea un tag anotado con el nombre v1.0.0. 
● -m "Primera versión estable": La opción -m añade un mensaje al tag, describiendo qué representa esa versión. 

Empujar el Tag al Repositorio Remoto 
# Ya que se haya creado el tag localmente, necesitas enviarlo al repositorio remoto para que esté disponible para otros colaboradores y sistemas de despliegue: 

sh 
● git push origin v1.0.0 

Listar Tags 
# Puedes ver todos los tags existentes en tu repositorio usando: 

Sh  
● git tag -a v1.0.0 -m 

# También puede mostrar una lista de todo lo creado. 

Borrar un Tag  

# Si necesitas eliminar un tag, puedes hacerlo local y remotamente: 

sh 

● git tag -d v1.0.0      # Eliminar localmente 
● git push origin --delete v1.0.0  # Eliminar remotamente 

# Análisis de commits: semantic-release dentro de esta se analiza los mensajes de commit , para así poder determinar automáticamente la próxima versión según las convenciones de commit. 

# Generación de changelogs: Se creará changelogs automáticamente basados en los commits. 

# Publicación de nuevas versiones: Que dentro de esta pueda automáticamente etiquete y publique la nueva versión. 

# Dentro de la automatización se pueda reducir el trabajo de manera manual para algunas versiones de tagging, así mismo poder garantizar que el versionado siga un patrón lógico basado en los cambios reales del código. También poder genera changelogs detallados, mejorando la documentación de las versiones. 

## Cangelog

# Mantengo el changelog actualizado: Cada vez que hago un cambio significativo en mi proyecto, aseguro registrar la modificación en el changelog. 
# Categorizo los cambios: Organizo las entradas del changelog en categorías como Added, Changed, Deprecated, Removed, Fixed, Security. Esto ayuda a los usuarios a comprender rápidamente los tipos de cambios realizados. 

Ejemplo ampliado de un changelog: 

[1.2.0] - 2025-01-15 

Added 

# Opción para usuarios de personalizar las notificaciones. 

Changed 

# Mejorada la interfaz de usuario para mayor accesibilidad. 

# Optimización del rendimiento en dispositivos móviles. 

Deprecated 

# Método antiguo de autenticación ahora está obsoleto. 

Removed 

# Eliminada la compatibilidad con versiones anteriores a Android 5.0. 

Fixed 

# Resuelto el problema de desincronización en tiempo real. 

Security 

# Mejora en la encriptación de datos del usuario. 