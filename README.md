# camaras-trafico-ha

A continuación te muestro como poner las cámaras de la DGT, dentro de tu instalación de Home Assitant.

Para que entiendas el funcionamiento básico de las cámaras de la DGT, estás no son vídeos en directo si no imagenes que van actualizandose cada pocos minutos. Podemos introducir estás imagenes dentro de tu instalación de Home Assistant, ya que estás imagenes se actualizan pero no se modifica su nombre.

Pasos a seguir:

1. Entrar en la web de la DGT a traves de esté enlace: https://www.dgt.es/conoce-el-estado-del-trafico/camaras-de-trafico
2. Utilizando los filtros, entrar en la cámara que queremos poner en nuestra instancia de Home Assistant.
3. Click derecho y "Abrir imagen en una pestaña nueva"
![image](https://user-images.githubusercontent.com/34164094/214644491-655452aa-6125-4ca4-8c75-4fae9570222e.png)
4. Copiaremos el enlace de la foto. (solo hasta .jpg)
![image](https://user-images.githubusercontent.com/34164094/214645678-1b7b6cc2-14bd-42fa-800e-108b2aae7738.png)
5. Entraremos a nuestro archivo de configuración en home assistant (/config/configuration.yaml)
6. Agregaremos una cámara:
