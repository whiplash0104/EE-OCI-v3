Instalar ANSIBLE BUILDER:

	$ curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
  	$ sudo yum install python3.9
	$ python3.9 get-pip.py
	$ python3.9 -m pip --version
	$ pip3 install ansible-builder==3.0.0

Compilar imagen de contenedor

	$ git clone https://github.com/whiplash0104/EE-OCI-v3.git
 	$ cd EE-OCI-v3/
	$ ansible-builder build -v 3 -t ee-oci

Push de imagen en registry con Podman

	$ podman login -u ${REGISTRY_NAMESPACE}/${USER} -p "${TOKEN}" ${REGION}.ocir.io
	$ podman tag localhost/ee_oci:latest ${REGION}.ocir.io/${REGISTRY_NAMESPACE}/${REGISTRY}:${TAG}
	$ podman push ${REGION}.ocir.io/${REGISTRY_NAMESPACE}/${REGISTRY}:${TAG}
