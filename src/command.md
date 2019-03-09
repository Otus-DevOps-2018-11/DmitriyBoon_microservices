docker run -d --network=reddit --network-alias=post_db --network-alias=comment_db mongo:latest
docker run -d --network=reddit --network-alias=post dmitriyboon/post:1.0
docker run -d --network=reddit --network-alias=comment dmitriyboon/comment:1.0
docker run -d --network=reddit -p 9292:9292 dmitriyboon/ui:1.0

docker run -d --network=reddit --network-alias=post_db --network-alias=comment_db mongo:latest
docker run -d --network=reddit --network-alias=post dmitriyboon/post:1.0
docker run -d --network=reddit --network-alias=comment dmitriyboon/comment:1.0
docker run -d --network=reddit -p 9292:9292 dmitriyboon/ui:2.0