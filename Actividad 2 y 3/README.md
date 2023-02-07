#### Link a repositorio en GitLab

Las siguientes actividades se encuentran realizadas en el repositorio de GitLab:

2 - Por un lado el proyecto en Django y ReactJs, Dockerizado con sus Dockerfile y su Docker-compose en la carpeta /deploy.

3 - Para finalizar, la pipeline esta en la carpeta fuente del proyecto, './gitlab-ci.yml' cada vez que se hagan cambios en la branch, se buildea y pushea las dos imagenes en Docker Registry. Si bien la actividad dice detectar los cambios de un index.html, tambien deje comentada dos lineas en las que unicamente inicia los scripts cuando se hacen cambios en ese archivo especifico.

(En proceso para hacer el deploy en una EC2 de AWS)

https://gitlab.com/sziinocolanino/docker-react-django
