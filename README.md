# drupal8dev
Drupal 8 dev playground using docker.

Using official Drupal 8 docker images, and using volumes for modules, themes and profiles which gets mapped to same folders inside the drupal container.

On OSX docker is slow because of slow mounts, so we are using docker-sync (http://docker-sync.io/)

# Usage
1. Copy .env-dist to .env
2. In root where we have docker-sync.yml file, start docker sync i.e. docker-sync start
3. Start docker compose e.g. docker-compose up -d

# Take backup of your development database
Use ./backup_db.sh this will create a backup called all-databases.gz inside ./backup folder. As official mysql container starts and any file in "docker-entrypoint-initdb.d" folder, which is mapped to ./backup folder is restored when mysql starts.
