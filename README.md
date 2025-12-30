docker compose build
docker compose up -d
docker compose exec jupyterhub datacube -v system init
docker compose exec jupyterhub datacube product add https://raw.githubusercontent.com/digitalearthafrica/config/master/products/esa_s2_l2a.odc-product.yaml


import datacube
dc = datacube.Datacube(app="test")
products = dc.list_products()
products


ref
https://hatarilabs.com/ih-en/how-to-set-a-multiuser-jupyterlab-server-with-jupyterhub-in-windows-with-docker

사용자 관리 페이지 : admin으로 로그인해서 해당 링크 직접 입력 후 접속
http://localhost:8000/hub/authorize

jupyterhub에서 제공하는 compose 파일을 사용하지 않은 이유
link: https://github.com/jupyterhub/jupyterhub-deploy-docker
-> 사용자 새로 생성할 때마다 사용자 각각의 도커 컨테이너가 추가됨