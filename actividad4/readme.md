
# Carlos Estuardo Monterroso Santos 201903767

## systemd unit de tipo servicio para ejecutar un script imprima un saludo y la fecha actual

Para crear un systemd unit de tipo servicio que ejecute un script que imprima un saludo y la fecha actual, sigue los siguientes pasos:

Crea un archivo de script en la ubicación que desees. Por ejemplo, puedes usar el comando nano para crear un archivo llamado saludo.sh con el siguiente contenido:

        echo "¡Hola! La fecha actual es $(date)."
Guarda el archivo y asegúrate de que sea ejecutable usando el comando

        chmod +x saludo.sh.

Crea un archivo de unidad de systemd para el servicio. Puedes usar nano para crear un archivo llamado saludo.service en el directorio /etc/systemd/system/ con el siguiente contenido:

        Copy code
        [Unit]
        Description=Servicio de saludo

        [Service]
        ExecStart=/ruta/a/saludo.sh
        Restart=always

        [Install]
        WantedBy=multi-user.target

Asegúrate de reemplazar /ruta/a/saludo.sh con la ruta correcta hacia tu archivo de script.

Guarda el archivo de unidad y recarga la configuración de systemd usando el comando systemctl daemon-reload.

Inicia el servicio usando el comando systemctl start saludo.service.

Verifica que el servicio está ejecutándose correctamente usando el comando systemctl status saludo.service.

Para hacer que el servicio se inicie automáticamente en el arranque del sistema, usa el comando systemctl enable saludo.service.

¡Listo! Ahora tu servicio de saludo debería estar funcionando correctamente y ejecutándose en segundo plano. Si deseas detener el servicio en algún momento, puedes usar el comando systemctl stop saludo.service.
