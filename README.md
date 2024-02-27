# JupyterQ

This is just a little help on how to run your own Jupyter Notebook server with the latest Q kernel and with your own license file.

## Prerequisites

 * You need a Linux running on an Intel CPU with Docker installed. You can get this on Windows 10/11 too if you [install WSL2](https://learn.microsoft.com/en-us/windows/wsl/install) and [Docker Desktop](https://www.docker.com/products/docker-desktop).
 * You need the l64 kdb binaries unzipped in a directory. The directory should at least contain `q.k` and `l64/q`.
 * You need a valid license file, typically a `kc.lic`. 
   
You can request and download a [free KDB personal edition with a 12 month free license here](https://kx.com/kdb-personal-edition-download/).
  
## Set up

Edit the relevant variables in the `.env` file. Those should point to your q home directory and your license file directory.
You can also modify the notebooks directory path and the server port if you need to.

## Start the Jupyter Notebook server

Go to the directory where the `docker-compose.yml` and `.env` file is and run the command below.
This will download the `kxsys/jupyterq` image to your computer (if not available yet) and start the server.

```
 $ docker-compose up -d          # or docker compose up -d
```

Open `http://localhost:8888`.

## Stop the Jupyter Notebook server

```
 $ docker-compose down           # or docker compose down
```

## Clean up

```
 $ docker rmi kxsys/jupyterq
```

