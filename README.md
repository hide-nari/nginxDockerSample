### settings

```bash
docker buildx build -t test-nginx:v1 . 
docker container run -d --rm --name nginx -p 8081:80 test-nginx:v1
docker container stop nginx
```

### access

- [http://localhost:8081/](http://localhost:8081/)
- [http://localhost:8081/one.html](http://localhost:8081/one.html)
- [http://localhost:8081/two.html](http://localhost:8081/two.html)