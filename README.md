# README

## Para colaborar (usando laragon):

* Instalar laragon for ruby on rails, por ejemplo en la carpeta C:/lararails/
* Crearse una cuenta en Github
* Hacer fork del repositorio ezetadevelop/ezpanel
* En el repositorio que se ha creado en nuestra cuenta, hacemos clic en "Clone or download" y copiamos el enlace
* En la consola del sistema, en la carpeta de nuestros proyectos, por ejemplo C:/lararails/www/, ejecutamos el comando:

    ```shell
    git clone https://github.com/..../ezpanel.git
    ```
* Accedemos a la carpeta que se acaba de crear: cd ezpanel
* Instalamos rubyonrails si no lo está ya:
    
    ```shell
    gem install rails
    ```
* Ejecutamos el comando:

    ```shell
    bundle install
    ```

## Actualizar nuestro repositorio con los cambios que hayan hecho otros colaboradores al repositorio principal
* Comprobar los repositorios remotos que tenemos configurados:

    ```shell
    git remote -v
    ```
    Nos deberían aparecer los dos (push y fetch) que apuntan a nuestro repositorio remoto.
* Añadimos el repositorio principal como upstream

    ```shell
    git remote add upstream https://github.com/ezetadevelop/ezpanel.git
    ```
* Descargamos los commits y los cambios del repositorio upstream:

    ```shell
    git fetch upstream
    ```
    Los cambios se guardan en nuestro repositorio local: upstream/master
* Nos aseguramos de estar en nuestra rama master:

    ```shell
    git checkout master
    ```
* Y mezclamos en ella los cambios de upstream/master:

    ```shell
    git merge upstream/master
    ```
    Si hubiésemos hecho cambios a nuestro código local, nos fallaría el merge y nos diría que tenemos que hacer stash:
    * Primero guardamos el trabajo actual en una pila:
    
        ```shell
        git stash
        ```
    * Una vez hecho el merge, aplicamos los cambios guardados:
    
        ```shell
        git stash apply
        ```
 * Ahora tenemos nuestra rama local master actualizada, tenemos que actualizar nuestro repositorio remoto:
 
    ```shell
    git push origin master
    ```