Build and push the image to docker hub:
docker build -t flask-server .
docker tag flask-server:latest <your-docker-hub-username>/flask-server
docker push <your-docker-hub-username>/flask-server
