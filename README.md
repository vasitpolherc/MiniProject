# MiniProject

Create a Service
1. Make sure that you are in the flower-api or uploadpage folder
2. Open your terminal and cd to project folder
3. Command in uploadpagefolder  : docker service create --name uploadpage -p 80:80 --network flower_net --replicas 3 vasitpolherc/uploadpage .
4. Command in flower-api folder : docker service create --name flower-api -p 8000:8000 --network flower_net --replicas 3 vasitpolherc/uploadpage .

Push your service to DockerHub
1. Command in uploadpagefolder  : docker push vasitpolherc/uploadpage
2. Command in flower-api folder : docker push vasitpolherc/flower-api

VM instance
1. Create 3 node on VM instance
2. Open Node1 VM
3. Command : docker network create -d overlay --attachable flower_net
4. Command : docker pull vasitpolherc/uploadpage
5. Command : docker pull vasitpolherc/uploadpage
6. Command : docker service create --name redis-flowerapp --network flower_net redis

Please enjoy
