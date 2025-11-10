Hacemos los comandos:
docker network create webnet
docker run --network webnet viaje-estudio
docker logs fiesta_app
docker build -t fiesta_app .
docker run --name fiesta_app --network webnet fiesta_app
docker run --name nginx_proxy --network webnet -p 8080:80 -v ./nginx/default.conf:/etc/nginx/conf.d/default.conf:ro nginx:1.27-alpine

Flask no se expone directamente para proteger el servidor de accesos no autorizados y para mejorar la seguridad. Mientras que Nginx, como reveser proxy, actua como un intermediario que recibe las solicitudes de los clientes, las procesa y las redirige al servidor de backend, mejorando el rendimiento y seguirdad
