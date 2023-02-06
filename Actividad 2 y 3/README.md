#### Link a repositorio en GitLab

Las siguientes actividades se encuentran realizadas en el repositorio de GitLab:
2 - Por un lado esta subido el proyecto de Django y ReactJs, Dockerizado con sus Dockerfile para cada repositorio, ademas del Docker-compose en la carpeta /deploy.
3 - Y para finalizar, la pipeline esta en la carpeta fuente del proyecto, './gitlab-ci.yml' cada vez que se hagan cambios en la branch, se buildea y pushea las dos imagenes para correr el proyecto. (En proceso para hacer el deploy en una EC2 de AWS automaticamente)

https://gitlab.com/sziinocolanino/docker-react-django
