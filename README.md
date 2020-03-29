This is a starter repository that helps you get setup with [`itzg/minecraft-server`](https://hub.docker.com/repository/docker/itzg/minecraft-server) containers that run FTB or CurseForge modpacks.

An example Docker Compose file has been created in [`valhelsia`](valhelsia).

## Setup
1. Download and place the corresponding modpack zip file in the [`modpacks`](modpacks) directory. See the [README there](modpacks/README.md) for a download link.

2. Go into the corresponding directory and bring up the Docker composition, such as
   ```
   cd valhelsia
   docker-compose up -d
   ```

   You can watch the logs by using
   ```
   docker-compose logs -f
   ```

The example will attach the container's `/data` path to the local directory `data/valhelsia`. You can adjust configuration in there and restart the container to pick up those changes.

It is recommended that you put the compose file for each in its own directory named with a short name so that it will be used as the Docker compose project name and show up nicely in `docker ps` listings, such as

```
CONTAINER ID        IMAGE                   COMMAND             CREATED              STATUS                                 PORTS                                 NAMES
b7fa79011ed6        itzg/minecraft-server   "/start"            About a minute ago   Up About a minute (health: starting)   0.0.0.0:25565->25565/tcp, 25575/tcp   valhelsia_mc_1
```

## Adding more

1. Duplicate and rename the `valhelsia` directory
2. In the copied `docker-compose.yml`
   1. Change the "valhelsia" part of the `/data` volume attachment
   2. Change the zip filename in `CF_SERVER_MOD` to the appropriate modpack you're adding
   3. If running alongside others from this starter, change the host port (left part) from 25565 to something distinct, like incrementing to 25566.
3. Download the **server** modpack file and place in `modpacks` along with the others
