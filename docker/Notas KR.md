Pasos para pedir el reporte:
Subir a la ultima version en el docker file
compilar: 
    docker build -t redhat-ubi8-jre11 .
generar tag luego de compilar: 
    docker tag redhat-ubi8-jre11 us-central1-docker.pkg.dev/lmtitest-intg-b162/baseimages/redhat-ubi8-jre11:TOREVIEW

docker run de la imagen, te metes dentro, saca evidencia de el paquete que esta instalado, te vas al cve y te fijas si tiene solucion

docker run -it 2ec9c5444778 bash
