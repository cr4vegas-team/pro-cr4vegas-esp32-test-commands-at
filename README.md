# Prueba de comandos AT por Serial

## Comandos

| Comando                                                     | Response                                    | Description                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------- | ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AT                                                          | OK                                          | ¡Haga ping al módulo para ver si está activo!                                                                                                                                                                                                                                                                                                                                                     |
| AT+CFUN=1                                                   | OK                                          | Esto habilita la funcionalidad completa del módem. Puede confirmar el estado del módem escribiendo AT + CFUN? De hecho, puede hacer esto con cada comando en el que establezca parámetros. Agregar un signo de interrogación inmediatamente después del comando, devuelve el valor actual de ese comando.                                                                                         |
| AT+CPIN?                                                    | +CPIN:READY                                 | Compruebe si la tarjeta SIM está lista para realizar llamadas, mensajes o para iniciar la transmisión de paquetes de datos.                                                                                                                                                                                                                                                                       |
| AT+CSTT="TM","",""                                          | OK                                          | Es necesario configurar el nombre del punto de acceso, el nombre de usuario y la contraseña antes de poder establecer la conectividad de datos. Utilice el nombre APN de su proveedor de tarjeta SIM . Tenga en cuenta que para la mayoría de los proveedores de servicios, el PIN y la contraseña no están configurados. Si su proveedor o usted lo ha configurado, por favor haga esto también. |
| AT+CIICR                                                    | OK                                          | Inicie la conexión inalámbrica con GPRS. Esto configura la conexión inalámbrica GPRS con el proveedor de servicios y obtiene una dirección IP                                                                                                                                                                                                                                                     |
| AT+CIFSR                                                    | 150.76.180.37                               | Obtiene la dirección IP asignada al módulo después de una conexión exitosa con los comandos anteriores                                                                                                                                                                                                                                                                                            |
| AT+CIPSTART="TCP","exploreembedded.com",80                  | OK CONNECT OK                               | Inicia una conexión TCP al sitio web en el puerto 80. El primer OK es la respuesta a la aceptación del comando y el segundo para la conexión exitosa.                                                                                                                                                                                                                                             |
| AT+CIPSEND=63                                               | >                                           | Este comando indica que realizaremos una solicitud HTTP cuya longitud es de 63 caracteres. Responderá con una matriz correcta, después de lo cual enviaremos la solicitud GET.                                                                                                                                                                                                                    |
| GET exploreembedded.com/wiki/images/1/15/Hello.txt HTTP/1.0 | SEND OK HTTP/1.0 200 OK \<respuesta> CLOSED | Realice una solicitud HTTP GET.                                                                                                                                                                                                                                                                                                                                                                   |

### Calidad de la señal

| Comando  | Respuesta            | Descripción                  |
| -------- | -------------------- | ---------------------------- |
| AT+CSQ=? | OK AT+CSQ +CSQ: 16.0 | Devuelve la calidad de señal |

Posibles valores
| Valor | dB  | Condicion |
| ----- | --- | --------- |
| 2     | -10 | Marginal  |
| 3     | -10 | Marginal  |
| 4     | -10 | Marginal  |
| 5     | -10 | Marginal  |
| 6     | -10 | Marginal  |
| 7     | -99 | Marginal  |
| 8     | -97 | Marginal  |
| 9     | -95 | Marginal  |
| 10    | -93 | OK        |
| 11    | -91 | OK        |
| 12    | -89 | OK        |
| 13    | -87 | OK        |
| 14    | -85 | OK        |
| 15    | -83 | Good      |
| 16    | -81 | Good      |
| 17    | -79 | Good      |
| 18    | -77 | Good      |
| 19    | -75 | Good      |
| 20    | -73 | Excellent |
| 21    | -71 | Excellent |
| 22    | -69 | Excellent |
| 23    | -67 | Excellent |
| 24    | -65 | Excellent |
| 25    | -63 | Excellent |
| 26    | -61 | Excellent |
| 27    | -59 | Excellent |
| 28    | -57 | Excellent |
| 29    | -55 | Excellent |
| 30    | -53 | Excellent |