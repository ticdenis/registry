## GitHub Registry

```shell script
# How to build a Docker image?
cd <folder> && docker build -t docker.pkg.github.com/$GITHUB_USERNAME/registry/<name>:<version> .

# How to login against GitHub registry?
docker login docker.pkg.github.com --username $GITHUB_USERNAME --password $GITHUB_TOKEN

# How to push a Docker image?
docker push docker.pkg.github.com/$GITHUB_USERNAME/registry/<name>:<version>
```
