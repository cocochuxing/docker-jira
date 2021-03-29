# docker-jira
docker jira

```shell script
sudo docker-compose build
sudo docker-compose up -d
sudo docker-compose down
sudo docker-compose up -d jira
sudo docker-compose up -d confluence
```

```yaml
confluence:
    #image: confluence/confluence:6.13.0
    build:
      context: confluence
      dockerfile: Dockerfile
    container_name: jira-confluence
    ports:
      - "8003:8090"
    volumes:
      - ./var/atlassian/confluence:/var/atlassian/confluence
      - ./share/confluence:/home/confluence
    depends_on:
      - mysql56
    restart: always
```

```
sudo docker-compose up -d
Creating network "docker_default" with the default driver
Creating jira-mysql ... done
Creating jira-fe         ... done
Creating jira-confluence ... done
```

```
sudo docker-compose down
Stopping jira-fe         ... done
Stopping jira-confluence ... done
Stopping jira-mysql      ... done
Removing jira-fe         ... done
Removing jira-confluence ... done
Removing jira-mysql      ... done
Removing network docker_default
```

Supported filenames: docker-compose.yml, docker-compose.yaml, compose.yml, compose.yaml

docker network create jira

WARNING: Found orphan containers (mysql, fe) for this project. If you removed or renamed this service in your compose file, you can run this command with the --remove-orphans flag to clean it up.
