# Cómo usar GitHub
## Colaborando con el proyecto de AREDN


### Creando una cuenta de GitHub
Para contribuir con el proyecto de AREDN, primero debes registrarte en GitHub. Esto es gratuito y fácil, lo puedes hacer siguiendo los siguientes pasos:

1. Abre en tu navegador la URL de GitHub: `https://github.com`.
2. Esto nos lleva a una web donde podemos registrarnos, introducimos un username, email, y contraseña. Sugerimos incluir el indicativo en el usuario. Ya tenemos nuestra cuenta.
3. En la página de GitHub, 'clickamos' en el botón que dice `Sign In` para entrar con nuestra cuenta.
4. Ya puedes buscar el proyecto de AREDN directamente en el buscador de la barra superior. Esto nos devolverá todos los resultados relacionados con el proyecto. O si solo queremos ir directamente al repositorio de firmwares podemos visitar: `https://github.com/aredn/aredn_ar71xx`.

### Entendiendo el ciclo de trabajo en GitHub:

El proceso de contribución y monitorizazión de los cambios en AREDN es crucial. Todo el código es mantenido en el repositorio MASTER de AREDN en GitHub. Para contribuir con una posible mejora al código del proyecto, debes primero hacer un FORK del repositorio MASTER de AREDN en GitHub. Esto creará una copia del repositorio en tu cuenta, sobre la que podrás hacer cambios sin afectar al resto de usuarios. Después CLONAR tu repositorio a tu máquina de desarollo para hacer los cambios y pruebas. 

Cuando estes satisfecho con tu trabajo, haz un COMMIT a tu copia local. Porfavor, se descritivo con el mensaje obligatorio adjunto a tu trabajo. Hace categorizar y evaluar los cambios más fácil. Ya , puedes hacer un PUSH a tu repositorio remoto para subirlo a tu cuenta de GitHub. Por último, solo faltaría crear un PULL REQUEST para notificar a los administradores del repositorio oficial que te gustaría que absorbieran tus cambios.

![GitHub Workflow](_images/GitHub-workflow.png)

#### Montando Nuestro Repositorio de trabajo:

1. Haz Log-in en tu cuenta de GitHub, y ve a `https://github.com/aredn/aredn_ar71xx`
2. Haz click en el botón de la parte superior derecha que dice `Fork`. Ya tienes una copia del código fuente de AREDN en tu cuenta de GitHub.
3. Ve a tu ordenador de desarollo y haz una copia del código (deberás haber instalado git): `git clone https://github.com/TuUsuarioVaEscritoAqui/aredn_ar71xx`
4. Ve al directorio `aredn_ar71xx`, ahora contiene tu copia local del proyecto oficial: `cd aredn_ar71xx`.
5. Una vez dentro del proyecto, podemos hacerle saber cual es el repositorio de origen inicial con:`git remote add aredn https://github.com/aredn/aredn_ar71xx`  

Ahora tu entorno local de GitHub sabe exactamente tanto de dónde viene originalmente el código, cómo dónde tenemos nuestra copia en GitHub.

#### Proceso Cíclico de Desarollo:

1. Actualiza tu entorno local con los últimos cambios realizados por el resto de la comunidad. Esto inculuirá cualquier cambio que tu hayas propuesto. *Cuidado:* Nunca hagas cambios directamente sobre la rama `develop`. Esto probablemente cause inconsistencias entre el repositorio principal y el tuyo.
	1. `git checkout develop` # Con esto nos cambiamos a la rama de desarollo.
	2. `git pull aredn develop` # Con esto nos sincronizamos los últimos cambios.
2. Creamos nuestra propia rama local dónde implementar nuevas funcionalidades o arreglar bugs:
	1. `git checkout -b my-wiz-bang-feature-name`
3. Realiza tus cambios y pruébalos. 
4. Cuando estes listo para subir tus cambios, comprueba que siguen funcionando con los últmos cambios. En la terminología de GitHub haz un "pull" y "rebasa" para aplicar tus cambios los últimos.  
	1. `git stash` Para salvar nuestros cambios sin aplicarlos.
	2. `git checkout develop`
	3. `git pull aredn develop`
	4. `git checkout my-wiz-bang-feature-name`
	5. `git rebase develop` Para mover nuestro trabajo a la rama con los ultimos cambios.
	6. `git stash pop` Aplicamos nuestros cambios
	7. Resolveremos cualquier posible conflicto con los nuevos cambios si somos avisados de alguno. 
	8. Comprobamos el correcto funcionamiento una vez más.
5. Ya podemos hacer un `Commit` con nuestros cambios a nuestro repositorio local. Para lueo hacer un `Push` a nuestra cuenta de GitHub.
	1. `git commit -m "Descripcion de los cambios realizados"`
	2. `git push origin my-wiz-bang-feature-name`
6. Para crear un `Pull Request` (PR) al repositorio MASTER de AREDN, vamos a `github.com//TuUsuarioVaEscritoAqui/aredn_ar71xx`, después seleccionamos la rama my-wiz-bang-feature-name. Hacemos click en el botón de `New Pull Request`. Ahora otros pueden revisar tus cambios, probarlos y darte su opinión. Si se decide que debes de hacer cambios, vuelve al paso 3. 
7. Una vez tus cambios son aceptados, puedes borrar tu rama:
	1. En tu copia local: `git branch -D my-wiz-bang-feature-name`
	2. En el Fork de tu cuenta de GitHub: `git push origin --delete my-wiz-bang-feature-name`

Y ya puedes contribuir con nuevas características comenzando de nuevo este ciclo.

#### Revision del trabajo de otros:
Para poder asegurarnos de que las contribuciones tienen la mayor calidad posible, es bueno que exista un proceso de revisión que permita introducir cambios de última hora. Esto se realiza durante la fase de "pull request". Antes de que sea aceptada, nuestra "pull request" queda abierta a comentarios. Para mas informacion sobre como hacer una revisión ver: 'https://help.github.com/es/github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request' 
