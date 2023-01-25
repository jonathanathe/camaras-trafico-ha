# camaras-trafico-ha

A continuación te muestro como poner las cámaras de la DGT, dentro de nuestra instancia de Home Assistant.

![20230125_192917](https://user-images.githubusercontent.com/34164094/214651478-e3267462-956c-4421-a4dc-08a8ac1e7a7b.gif)


Para que entiendas el funcionamiento básico de las cámaras de la DGT, estás imágenes no son vídeos en directo sino imágenes fijas que van actualizándose cada pocos minutos. Podemos introducir estás imágenes dentro de Home Assistant, ya que estás imágenes se actualizan, pero no se modifica su nombre

Pasos a seguir:

1. Entrar en la web de la DGT a través de esté enlace: https://www.dgt.es/conoce-el-estado-del-trafico/camaras-de-trafico
2. Utilizando los filtros, entrar en la cámara que queremos poner en nuestra instancia de Home Assistant.
3. Clic derecho y "Abrir imagen en una pestaña nueva"
![image](https://user-images.githubusercontent.com/34164094/214644491-655452aa-6125-4ca4-8c75-4fae9570222e.png)
4. Copiaremos el enlace de la foto. (solo hasta .jpg)
![image](https://user-images.githubusercontent.com/34164094/214645678-1b7b6cc2-14bd-42fa-800e-108b2aae7738.png)
5. Entraremos a nuestro archivo de configuración en home assistant (/config/configuration.yaml)
6. Agregaremos una cámara de la siguiente manera y poniendo la URL de la foto que obtuvimos antes:
```
camera:
  - platform: generic
    name: MA-19 - 1
    still_image_url: "https://infocar.dgt.es/etraffic/data/camaras/1398.jpg"
    verify_ssl: false
```
7. Guardamos y reiniciamos nuestra instancia.
8. Luego nos quedara solo crear una card con las cámaras, en mi caso uso la card de frigate.

```
type: vertical-stack
cards:
  - type: custom:mushroom-title-card
    title: MA-19
  - type: custom:frigate-card
    cameras:
      - camera_entity: camera.ma_19_1
    dimensions:
      aspect_ratio_mode: unconstrained
    timeline:
      show_recordings: false
    live:
      preload: true
      auto_play: all
      lazy_unload: all
      draggable: true
      lazy_load: true
    view:
      default: live
      update_force: false
      timeout_seconds: 0
      update_seconds: 0
    menu:
      buttons:
        frigate_ui:
          enabled: false
```
¡Y eso es todo, espero que os sirva y que podáis disfrutar cada vez más de vuestra instancia de Home Assistant!

