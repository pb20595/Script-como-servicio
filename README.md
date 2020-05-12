# Script-como-servicio
Generación de un servicio windows a partir de un script en powershell para que siga funcionando el script aunque haga sign out el usuario correspondiente.

Funciona de la siguiente forma:

Definimos variables dentro de powershell:

-Nombre que daremos a nuestro servicio:

$NombreServicio = 'DesplieguesAzureIBERIA'

-Ruta del ejecutable de PowerShell:

$RutaPowershell = 'C:\WINDOWS\System32\WindowsPowerShell\v1.0\powershell.exe'

-ExecutionPolicy para asegurarnos de que no se bloquea la ejecución del script e indicamos con file  la ruta de nuestro script:

$Argumentos= '-ExecutionPolicy Unrestricted -File C:\Utils\scriptdespliegues.ps1'

Para la instalación del servicio ha hecho uso de nssm que lo genera como servicio de la siguiente forma:

-En la ruta en la que se encuentre nssm

.\nssm install $NombreServicio $RutaPowershell $Argumentos

Obtenemos:

Fuente utilizada: https://sobrebits.com/ejecutar-script-de-powershell-como-servicio-de-windows/

nssm: https://nssm.cc/download
