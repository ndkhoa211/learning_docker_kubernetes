**CONCLUSION:**
1. `docker network create goals-net`
2. `docker run --name mongodb -v data:/data/db --rm -d --network goals-net -e MONGO_INITDB_ROOT_USERNAME=khoa -e MONGO_INITDB_ROOT_PASSWORD=nguyen mongo`
3. `docker build -t goals-node .`
4. `docker run --name goals-backend -v "C:/Users/user/Desktop/learning_docker_kubernetes/multi-container-app/backend:/app" -v logs:/app/logs -v /app/node_modules -e MONGODB_USERNAME=khoa -e MONGODB_PASSWORD=nguyen --rm -d -p 80:80 --network goals-net goals-node`
5. `docker build -t goals-react .`
6. `docker run -e WATCHPACK_POLLING=true -v "C:/Users/user/Desktop/learning_docker_kubernetes/multi-container-app/frontend/src:/app/src" --name goals-frontend --rm -d -p 3000:3000 -it goals-react`