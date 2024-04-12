# KCD Madrid - 2024 website

## Develop

To develop, just run this command and open your browser at http://localhost:1313. When making changes in the code, the website will be automatically regenerated. You just need to refresh the browser.

```bash
docker run -it --rm --name kcdmadrid2024 \
  -v $(pwd)/:/root/kcd/ \
  -p 1313:1313 \
  kcdmadrid:2024
```

Generate output folder:
```bash
docker run -it --rm --name kcdmadrid2024 \
  -v $(pwd)/:/root/kcd/ --entrypoint hugo \
  -p 1313:1313 \
  kcdmadrid:2024
```

## Build

We have containerized the KCD Madrid 2024 webpage. To avoid compatibility problems and versions mismatch you can execute and run the website using docker/podman. To do so, make sure you have initialized and pulled the submodules.

```bash
git submodule update --init --force
docker build -t kcdmadrid:2024 .
```

## Execute

To execute and serve the website you can run the following command, remember hugo uses the port 1313.

```bash
docker run -p 1313:1313 kcdmadrid:2024
```
