# homebox install

services:
  homebox:
    image: ghcr.io/sysadminsmedia/homebox:latest
#   image: ghcr.io/sysadminsmedia/homebox:latest-rootless
    container_name: homebox
    restart: always
    environment:
    - HBOX_LOG_LEVEL=info
    - HBOX_LOG_FORMAT=text
    - HBOX_WEB_MAX_FILE_UPLOAD=10
    # Please consider allowing analytics to help us improve Homebox (basic computer information, no personal data)
    - HBOX_OPTIONS_ALLOW_ANALYTICS=false
    volumes:
      - /home/kris/docker/homebox:/data/
    ports:
      - 3100:7745

volumes:
   homebox:
     driver: local
