### settings

```bash
docker buildx build -t test-nginx:v1 . 
docker container run -p 8080:80 test-nginx:v1
```

### access

[http://localhost:8080/](http://localhost:8080/)

[http://localhost:8080/one.html](http://localhost:8080/one.html)

[http://localhost:8080/two.html](http://localhost:8080/two.html)