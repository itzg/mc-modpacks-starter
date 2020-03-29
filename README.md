This is a starter repository that helps you get setup with `itzg/minecraft-server` containers that run FTB or CurseForge modpacks.

An example Docker Compose file has been created in [`valhelsia`](valhelsia); however, you will need to download and place the corresponding modpack zip file in the [`modpacks`](modpacks) directory. See the [README there](modpacks/README.md) for a download link.

Go into the corresponding directory and bring up the Docker composition, such as

```
cd valhelsia
docker-compose up -d
```

The example will attach the container's `/data` path to the local directory `data/valhelsia`. You can adjust configuration in there and restart the container to pick up those changes.