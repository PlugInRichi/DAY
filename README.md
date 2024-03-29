
# DAY (Detección de Armas con YOLO)

## Instalación 🚀

### En linux

Crear ambiente

```
virtualenv -p python3.7 env
```

Activar el ambiente

```
source env/bin/activate
```

Instalar librerias 

```
pip install -r requirements.txt
```

Será necesario descargar los pesos y ponerlos en una carpeta llamada checkpoints

>https://drive.google.com/drive/folders/1UZPEwQVwIw_cXa9jwf3TLV63T3YfqLjT?usp=sharing

## Ejecución 🕹️



La siguiente ejecución utilizando la web cam puede realizarse de la siguiente manera
> python deteccion_video.py --model_def config/yolov3-custom.cfg --class_path custom/classes.names  --weights_path checkpoints/yolov3_ckpt_24.pth  --conf_thres 0.95

![Sistema en uso](videos/Ejemplo.PNG)

Si se quiere probar utilizando un video debería ejecutarse de la siguiente manera
>python deteccion_video.py --model_def config/yolov3-custom.cfg --class_path custom/classes.names  --weights_path checkpoints/yolov3_ckpt_24.pth  --conf_thres 0.95 --directorio_video videos/tiro.mp4 --webcam 0

Para activar la función de correción de contraste puede añadirse la siguiente bandera:
>--high_contast


Adicionalmente para evaluar su rendimiento puede hacerse mediante el comandos:
 >python testv2.py --model_def config/yolov3-custom.cfg --class_path custom/classes.names  --weights_path checkpoints/yolov3_ckpt_24.pth --batch_size 2 --data_config  config/custom.data
 
