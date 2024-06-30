
# Pasito a Pasito: 
# Cómo Generar una Clave SSH con Ed25519 y Configurarla en GitHub 🔐

Una clave SSH es un par de claves criptográficas que se utilizan para autenticar y asegurar las conexiones entre un cliente y un servidor a través del protocolo Secure Shell (SSH). 
Ed25519 es un algoritmo moderno y seguro para la generación de claves SSH. 
Sigue estos pasos para crear una clave con alta seguridad.


## 1. Abrir la Consola de GIT BASH
Abre la consola de GIT BASH.

## 2. Ejecutar el Comando para Generar la Clave
Ingresa el comando, incluye el correo electrónico que tienes vinculado a GitHub:

      ssh-keygen -t ed25519 -C "tu-email@gmail.com"


## 3. Confirmar la Generación de la Clave
Es esperable ver:
>Generating public/private ed25519 key pair.

Presiona ENTER.

## 4. Confirmar Ubicación de la Clave
Es esperable ver:
 >Enter file in which to save the key (/c/Users/NombreUsuario/.ssh/id_ed25519): Created directory '/c/Users/NombreUsuario/.ssh'.

Presiona ENTER para aceptar la ubicación predeterminada.

## 5. Introducir Frase de Contraseña (Opcional)
Es esperable ver:
>Enter passphrase (empty for no passphrase):

Presiona ENTER.

## 6. Repetir Frase de Contraseña
Es esperable ver: 
`Enter same passphrase again:`
Presiona ENTER.

## 7. Verificar la Generación de la Clave
Es esperable ver:

>Your identification has been saved in /c/Users/NombreUsuario/.ssh/id_ed25519
Your public key has been saved in /c/Users/NombreUsuario/.ssh/id_ed25519.pub
The key fingerprint is:
SHA256:1++TPAVbn61tJmCyoYVPBoiybpBU5/nyxmL3+VwPM6cPK1E tu-email@gmail.com

## 8. Iniciar el Agente SSH
Ingresa el siguiente comando:

      eval "$(ssh-agent -s)"

Es esperable ver: 
>Agent pid 123

## 9. Añadir la Clave SSH al Agente
Ingresa el siguiente comando:

      ssh-add ~/.ssh/id_ed25519

Es esperable ver: 
>Identity added: /c/Users/NombreUsuario/.ssh/id_ed25519 (tu-email@gmail.com)

## 10. Copiar la Clave Pública
Ingresa el siguiente comando para copiar la clave pública:

      clip < ~/.ssh/id_ed25519.pub


## 11. Añadir la Clave SSH a GitHub
1. Ve a la web de GitHub, inicia sesión y ve a `Settings`.
2. En la barra lateral de configuración de usuario, da clic en `Llaves SSH y GPG`.
3. Haz clic en `New SSH key` o `Add SSH key`.
4. En el input `Title`, ingresa un nombre que identifique la PC. Ejemplo: "Notebook de usuario".
5. En el input `Key`, pega la clave copiada.
6. Haz clic en `Add SSH key`.
7. Si te lo pide, confirma tu contraseña de GitHub.

## 12. Configurar Git con tu Nombre y Correo Electrónico
1. Al volver a Git, ejecuta:

        git config --global user.name "Your Name"
        git config --global user.email "you@example.com"

2. Realiza el push, copia, pega y ejecuta el comando sugerido.


Si encontraste útil este tutorial, te invitamos a compartirlo con otras personas que puedan beneficiarse de él. 
También puedes mencionarnos en tus redes sociales o en tu comunidad

>[LinkedIn](https://www.linkedin.com/in/africaaular/)
[Github](https://github.com/AFRIAULAR)
**AfriCode{💜}**