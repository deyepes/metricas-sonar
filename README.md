# Métricas en sonar
Proyecto para crear servidor sonar desde docker.

### Herramientas:

Dillinger uses a number of open source projects to work properly:

* [Docker] - Debug your app, not your environment
* [Sonarqube] - Your teammate for Code Quality and Security

### Pasos:

**1.**	Tener el proyecto base para el ejemplo tomado de [sprint boot][Sprint Boot] en GitHub.
**2.**	Instalar sonar desde docker.  Sino está instalado instalarlo desde [docker][Docker]

```sh
$ docker pull sonarqube
```
**3.** Correr el sonarqube:
```sh
$ docker run -d --name sonarqube -p 9000:9000 sonarqube
```
**4.** Verificar que corre abriendo el servidor local https://\<localhost\>/9000
  
**5.** Descargar [Sonar-scanner]
  
**6.** Descomprimir en un directorio deseado.

**7.** Establecer el sonar-scanner como variable de entorno.

**8.** Configurar el sonar-scanner.properties apuntando al servidor

` sonar.host.url=https://<localhost>/9000 
`

**9.** Agregar el sonar-project.properties en la raiz del proyecto a analizar con los siguientes datos:

`       sonar.projectKey=rest-service`

`       sonar.projectName=rest-service`

`       sonar.projectVersion=1.0`

`       sonar.java.binaries=./build/classes`


**10.** Ejecutar el sonar-scanner en nuestro proyecto.

```sh
$ sonar-scanner
```

**11.** Verificar nuestro código en https://\<localhost\>/9000  buscando nuestro proyecto.

### Y ya nos debe mostrar el análisis de nuestro proyecto.



[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)


   [Docker]: <https://www.docker.com/>
   [Sonarqube]: <https://www.sonarqube.org/>
   [Sprint Boot]: <https://github.com/spring-guides/gs-spring-boot>
   [Sonar-scanner]: <https://docs.sonarqube.org/latest/analysis/scan/sonarscanner/>
