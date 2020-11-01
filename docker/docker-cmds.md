docker commands

docker tag local-image:tagname new-repo:tagname

docker push ziaur25/myrepo:tagname

Docker

Tag image:

docker tag &lt;user&gt;/&lt;image&gt; &lt;your\_user&gt;/&lt;new\_image_name&gt;

docker tag karthequian/helloworld ziaur25/myrepo

Push image:

docker push ziaur25/myrepo

docker push &lt;user&gt;/&lt;image&gt;

——

docker machine0image

docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <<docker-name

docker run -d --rm -p 1234:1234 ziaur25/docker-jetbrain-server

docker run -d --rm -p 4040:4040 ziaur25/docker-jetbrain-server