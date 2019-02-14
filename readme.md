-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Software Instalacion Modulos
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Obligatorios
•	Java versión jdk1.8.0_144
•	Copia de los 4 módulos (PC, CC, BC y AB)

Recomendados
•	Sourcetree (luego de instalar, reiniciar la pc)
	Agregar el proxy al source tree: araprx1.rsa-arg.com.ar puerto: 3128
	En network, tildar la opcion "add proxy server configuration to git/mercurial"

•	DCEVM-light-8u112-installer (no necesario)
•	SOAP UI

variable de entorno "JAVA_HOME" valor: "C:\Program Files\Java\jdk1.8.0_144"
Variable de entorno "path" agregar al valor ";%JAVA_HOME%\bin"

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Instalacion Modulos
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

0. Entrar a la carpeta del modulo a clonar
1. entrar a https://bitbucket.org/dashboard/overview
2. seleccionar el modulo a descargar. Ej: Claim Center (CC)
3. copiar la url (https://diegodecara@bitbucket.org/suraargentina/claim-center.git)
4. abrir el source tree, seleccionar una solapa nueva e ir a clone.
5. En el source path / url pegar la direccion copiada previamente y agregar ".git" al final. 
6. En el destination path buscar la carpeta del modulo y entrar al subdirectorio "modules". Y hacer click en seleccionar.
7. Click en clonar.
8. En Sourcetree ir a REMOTES/origin y dar doble click a develop
9. En la ventana que aparece dar ok. Aparecera develop como una rama local (en BRANCHES)
10. Ir a submodules y desplegar configuration hasta suite, y dar doble click en suite
11. Darle click a GitFlow --> OK (esto genera un branch: develop) Se hace por cada modulo la primera vez o sino Ir a REMOTES/origin y dar doble click a develop
12. En la ventana que aparece dar ok. Aparecera develop como una rama local (en BRANCHES)
13. En C:\gw\CM\modules\configuration\plugins\shared\basic\lib copiar commons-configuration-1.9.jar y jjwt-0.2.jar
13.1 Para el modulo de CC copiar el contenido de la carpeta \\arlap437\gw\Archivos instalacion\jars CC a C:\gw\CC\modules\configuration\plugins\shared\basic\lib
14. Copiar carpeta scripts en modules (compartido de pato)
15. pararse en c:\gw\bc
16. mantener shift + boton derecho --> Abrir ventana de comandos aqui
17. correr gwb clean
18. correr gwb cleanideaoa
19. correr gwb compile (compilar)
20. correr gwb studio (inicializa el IDE) o gwb runserver (inicializa el modulo en CONSOLA)
21. Luego de que termine de indexar, cambiar la configuracion a server y dar play.

************ HACER ESTO, EL DETALLE ESTA EN EL MAIL: RV: Acelerador RTM - Configuración del Studio **************

1.	Abrir el Studio
2.	Elegir el menú “File -> Project Structure” (Ctrl+Alt+Shirt+S) para abrir la pantalla de configuración. Seleccione “Modules” y en seguida la pestaña “Dependencies”:
3.	Agregue el archivo “./modules/configuration/deploy/WEB-INF/lib/perf-tools90SLF4J.jar” como una dependencia del tipo “Compile”:
4.  Seleccione el archivo: perf-tools90SLF4J.jar
5.	Aplique las configuraciones:
6.	Recompile la aplicación “Build -> Make Project” (Shift + F9). Listo!

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Instalacion Scrapchat
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Scrapchat snapchat mapchat
0. abrir el cmd con permisos de administrador
0. y ejecutar desde la linea de comandos 
1. Instalar el DCEVM-light-8u112-installer
2. elegir  la version jdk 1.8 144	
3. tocar en el boton Replace 

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
--  Comandos GIT
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-Configuracion GIT en Sourcetree:

git config --global http.proxy http://pmolina:Messi2022@araprx1.rsa-arg.com.ar:3128
git config --global https.proxy http://pmolina:Messi2022@araprx1.rsa-arg.com.ar:3128

-Rollback de un commit en una rama: 
git reset --soft HEAD~;

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- URLs
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

LOCAL: 
http://localhost:8280/ab
http://localhost:8580/bc/BillingCenter.do
http://localhost:8080/cc/ClaimCenter.do
http://localhost:8180/pc/PolicyCenter.do

DEV:
https://ssurgwsoadev3.opc.oracleoutsourcing.com/pc/PolicyCenter.do

QA: 
https://ssurgwsoadev4.opc.oracleoutsourcing.com/pc/PolicyCenter.do
https://ssurgwsoadev4.opc.oracleoutsourcing.com/bc/BillingCenter.do

PRE: 
https://i-preproducciongestion.segurossura.com.ar/cc/ClaimCenter.do
https://i-preproducciongestion.segurossura.com.ar/pc/PolicyCenter.do

PROD:
https://i-gestion.segurossura.com.ar/pc/PolicyCenter.do

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Como Cargar pequeño
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. Entro url policy
2. alt shit t
3. datos de muestra de pc
4. click en pequeño (localidades, cuenta, polizas)
5. Modificar la fecha del sistema para adelante. para cambiarla dropdb. 
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Como Cargar archivo de la muerte.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. cargar el pequeño.
2. desde policy: administracion, utilidades, importar datos
3. Buscar el archivo dataloder en la carpeta C:\gw\PC\modules\configuration\config\import\admin
4. Sobreescribir todos los registros existentes
5. finalizar

Establecer nivel de registro: para marcar el nivel del logeo. 
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Refacturacion
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

clase: UpdateTermBach sura
si se agrega una columna o una entidad: ir al arachivi extension.properties y subir un numerito en la version

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Como agregar una rama para desarrollar.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1. Entrar al bitbucket.
2. Entrar a PC o al modulo a desarrollar.
3. Darle click en el + 
4. Create Branch
5. En "Branch From" buscar el release
6. En "Branch Name" completar con la nomenclatura: BUGFIX/DEXXX o BUGFIX/USXXXX donde XXX es el numero del defecto o la historia de usuario, y al final un nombre descriptivo de la historia: "bugfix/US5663 Bugs Usabilidad Web Productores" por ej
7. Ir a Source Tree
8. Click en Fetch (actualiza los branchs creados los cambios de contenido/estructuras)
9. Ir a remotes/origin/bugfix y buscar el nombre del branch creado.
10. Doble click ahi y ok en el cartel que aparece.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Como ver en CA las tareas.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. logearse en rally1.rallydev.com
2. seleccionar Sura Argentina - R1 - Stabilization
3. Ir al menu Track y luego dar click en Team Status
4. Buscar por nombre y abrir con el +
5. Del lado izq se ven las tareas y del derecho la historia.
6. Ingresar a la tarea y completar con las horas que restan por terminar.
6.1 Si se le da click a la historia en la columna de la derecha, esta el excel con mas informacion 
7. Si faltan horas ir a la rueda de la derecha y copiar la tarea con la cantidad de horas estimadas que faltan para terminar.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Para entrar a Product designer (widget):
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

en una ventana de cmd (la de PC)
cd productdesigner
cd bin
ejecutar launchpd
pw gwgw

System tables

Luego de agregar los valores:
1. Disquete (guardar)
2. flecha <<< 	
3. Validar
4. Comitt
5. Rueda Syncronize system table

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Generar PR
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Cosas a tener en cuenta antes de generar el PR:
1. Los metodos, clases, entidades, etc creadas deben tener SURA al final
2. Los IF por mas que sean de una linea deben tener { } (llaves)
3. Los and, or, etc deben tener letras en minusculas.


1. Nomenclatura: DE### [XX] Descripcion breve del cambio\" o \"TFS### [XX] Descripcion breve del cambio\" o \"CONFIG [XX] Descripcion breve del cambio\" (XX = Iniciales del developer o responsable)
2. Stage all para que agregue todos los cambios listos para el commit (habilita el boton)
3. commit
4. click derecho en el brach, 	create pull request  (hace validaciones de codigo codenarc, si falla no genera el pull request y no abre la web)
5. SE abre la web del bit bucket, se busca el destino donde se quiere hacer el pull request. 
6. DEscription es el titulo que aparece y el titulo real es una parte de la url (bugfix/US5663-Bugs-Usabilidad-Web-Productores)
7. Agregar los reviewers
8. darle a create pull request.
9. Revisar conflictos (aparecen en amarillos con una C), bajar la ultima version del release (pull) y resolver los conflictos locales y realizar todos los pasos nuevamente. 
10. Volver al sourcetree, generar un nuevo pull request para desarrollo siguiendo los mismos pasos desde el pull request.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Mergear release con el branch.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. bajar el nuevo release
2. doble click en el release para bajarlo
3. boton derecho en el release y merge dentro del current branch

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Hotkeys
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. Alt+Shift+E navegador, te lleva al código
2. Alt+Shift+L recargar código en el navegador
3. Shift+ShifT Buscar archivos en la solución
4. Ctrl+Shift+F Buscar código en la solución
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------	

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Rating engine
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

entra por la clase, ordena las coberturas y por cada una llama una rutina. 
las rutinas se van ejecutando, y cada una llama una o mas tablas.

las tablas estan en el libro de tasas (administracion, clasificacion, libro de tasas).
hay un libro por cada ramo.

buscar rutina submissionfee


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Replicar Libro de Tasas en los diferentes ambientes
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1. Administracion --> Clasificacion --> Libro de tasas.
2. Buscar --> Motor -- Promover a Etapa
3. Sino funciona
4. Exportar 
4. Alt shif + T --> Reload Ramo Ratebook (SURA) (Carga una version anterior)
5. Volver a Administracion --> Clasificacion --> Libro de tasas.
6. Motor.
7. Seleccionar el Nombre a cargar.
8. Regresar al borrador.
9. Importar el xml.
10. Promover etapa (en dev no hace falta)

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Procesos Batch:
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
PolicyChangeCertificateBatchSura.gs

1. alt shit t
2. Herramientas del servidor.
3. Informacion de proceso por lotes.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Para Cambiar la fecha de sistema:
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1. alt shit t
2. Reloj de Sistema
3. Prueba de reloj 
4. Cerrar sesion e iniciar.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Para cambiar el estado de una poliza a mora:
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1. Pasar la fecha del sistema a 1 dia despues de la fecha de facturacion
2. Correr el batch de factura vencida primero y despues factura.
3. Avanzar 1 dia despues de la fecha de vencimiento y correr los batch de nuevo.

avanzo 1 dia despues de la fecha de vencimiento de la factura y otra vez corro los batch.|

ahi deberia aparecer la mora
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Cargar libro de tasas
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
primero  actualizar  clase DataLoaderProducerCodeSura, linea 115 y cambiar por "su" (hay una manera de ejecutar esto por pantalla tambien )

1. Ejecutar en el scratchpad:
Ir Administracion --> parametros de secuencia --> ViewLoadProducerInfoButtonSura: true
Clasificacion --> Actualizacion Masiva de Tarifa --> Cargar informacion actual.

uses ar.com.sura.pc.dataloader.DataLoaderProducerCodeSura

var dataloader = new DataLoaderProducerCodeSura()
dataloader.update()

2. Cargar el libro de tasas de los 3 ramos


En el caso que tengan que hacer un drop, primero tiene que importar los siguientes
sura_producercode_info.xml
sura_producer_info.xml
Y posteriormente ejecutar el update del paso1

pc\modules\configuration\config\resources\systables\sura_producercode_info.xml

pc\modules\configuration\config\resources\systables\sura_producer_info.xml

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Error oferta no valida: 
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Si es en local: Cargar libro de tasas
Alt + shift + t 
Reload AUTO Ratebook (SURA) --> ejecutar

Si es en QA: cargar la cotizacion del dia en al tabla tcambio de intergacion a la fecha a la que se movio qa
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Agregar Parametro de Secuencia.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Se agrega por el codigo: ScriptParameters.xml y ScriptParametersEnhacement.gsx
Se utiliza: ScriptParameters.NombreDelScriptParameter
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Error de validacion al subir el codigo
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1. Navegar en el IE/Chrome el siguente archivo
	C:/gw/PC/modules/tools/static_analysis/reports/pc-CodeNarcReport.html
	
2. Ubicar si se modificó algunos de los archivos listados al final de la pantalla.
3. buscar la linea del error en el codigo.
4. Modificar y volver a subir.
5. Profit	

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Renovar
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1. Tiene que estar levantado billing y claim
2. Parado en el resumen de la poliza, Nuevo --> Renovar
Pagar la poliza en billing center: 
	1. Buscar la poliza.
	2. Con el numero de poliza ir a cuenta.
	3. Acciones --> Pago Nuevo. --> Nuevo Pago de Factura Directa.
	4. Seleccionar la poliza.
	5. Completar con el monto total 
	7. Número de autorizacion aleatorio
	8. Tipo de tarjeta. 
	9. Click en Ejecutar sin distribución.


Si se renovo con error, se puede poner la poliza como no renovable y luego Retirar la transaccion.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Resolver conflicto
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
0. Copiarse las modificaciones que dan conflictos a un txt.
1. Actualizar develop o la rama a mergear.
2. Pararse en la rama del desarrollo.
3. click derecho en develop o la rama a mergear y clickear en: merge develop into current branch.
4. En file status se muestran los conflictos, botton derecho al archivo y seleccionar "Resolve conflicts --> Using Theirs. 
5. Ir al studio y modificar los archivos luego de que recarguen pegando lo salvado previamente en el txt.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Crear parches
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1. Crear una rama local basada en la rama a la que se van a subir los cambios
2. Pararse en develop y buscar el commit 
3. Buscar el commit que se quiere parchear
4. Boton derecho crear parchear
5. Crear archivos por orden en los que se modificaron
6. Luego pararse en la rama generada, menu actions --> Apply Patch
7. Buscar el archivo, opcion working copy, y aplicar.
8. Si hay conflictos se genera un archivo basura, copiar lo que hay que modificar y pegarlo en el archivo real
9. Luego de aplicar todos los parches, compilar y comitear.
10. Generar el PR a la rama deseada.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Ver Log 
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
1. alt shift  t
2. Ver registros
3. buscar archivo pc-log.log
	      archivo plugins.log esta el job de endoso masivo


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Modificacion de UW por codigo.
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-systables.xml contiene la base de .xml donde estan las configuraciones de las coberturas.
en coerableUtil o linea + underwriterEValuatorSura.gs esta el codigo de las reglas.

en CoverableUtilQueryHandlerSura.gs estan los Query.Make que cargan en memoria los xml. 
Con los nombres de las entidades se pueden rastrear en systables.xml

Luego de modificar el .xml y exportarlo, ir a modificar las 2 primeras lineas por:

<?xml version="1.0"?>
<import>

Si queda mal el .xml con cosas que faltan:
abrir el product designer
system tables
chequear si es el modificado, sino bajar y subir.
modificar una linea cualquiera
guardar con el disquete
flecha para la izq
commit
esperar a que desaparezca
volver y poner la linea como estaba anterior
guardar
commit
esperar que desaparezca
chequear si en el sourcetree fue bien

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Polizas Madres	
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-Plan enlatado: Cencosud 1159
La vigencia de la poliza madre debe comenzar un primero del mes.

-el job que corre a fin de mes y genera los endosos se llama: "Endoso Pólizas Madres" 

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Reglas de suscripcion (AAH : Edad entre 14 y 65)  / Perfiles de autoridad (BU 2A, BU2C, etc)
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Administracion --> Configuracion Comercial --> Reglas Comerciales --> Reglas de Suscripcion.

Son los UW, se pueden crear por codigo o por la aplicacion.

Cuando tienen configurado un comparador, se le pasa un parametro.

En Administracion --> Usuarios --> Perfiles de Autoridad se configura la regla con la comparacion.

Para exportar la Regla de suscripcion: 

1. Ir a la regla de suscripcion, ascender a etapa, promocionar aprobada.
2. copiar a C:\gw\PC\modules\configuration\config\import\bizrules
3. seleccionar --> Mas --> exportar seleccionada.
4. modificar el nombre

Para importar la Regla de suscripcion: 
1. Administracion --> Configuracion Comercial --> Reglas Comerciales --> Estado de importacion/exportacion
2. Importar archivo
3. C:\gw\PC\modules\configuration\config\import\bizrules y buscar el archivo
4. Importar y darle F5 hasta que termine
5. Importacion completa
6. Seleccionar y Aplicar Seleccionado

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-- Usuarios
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

sfavelukes 2A
galvarez 1E 
aburnes 1C
dgaudenzi 2E

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Cola de Mensajes
----------------------------------------------------------------------------------------------------------------------------------
Administracion-->supervision-->Cola de Mensajes


tema topeos que estuvo viendo ruben
CA7RatingEngine
calculateMinMaxPercents



----------------------------------------------------------------------------------------------------------------------------------


PATENTE: EIG202
PQW008

cuit: 30715002120

tarjetas
visa: 4012888888881881
amex: 378734493671000


String empty

uses org.apache.commons.lang3.StringUtils
StringUtils.Empty

gwb dropdb borra la base de datos local

policy line: muestra las coberturas cargadas
policy: coverableUtil.gs

submission wizard = emision
policy change wizard = endoso
renewal wizard = renovacion

Suscripcion (Under writer)
linea + underwriterEValuatorSura.gs


miercoles 28 10 a 13 hs.


gasto adquisision : recargo administrativo
gasto explotacion : derecho de emision + asistencia

administracion utilidades, parametros de secuencia, PersistSubmissionQuoteCR cambiar a true