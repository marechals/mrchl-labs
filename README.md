# MRCHL Labs

Static HTML and CSS site for `mrchl.com`, including the home page, `/projects/`, and `404.html`.

## Deploy on the Mac mini with Docker

The nginx container should serve this repository directly from `/usr/share/nginx/html`.

1. Clone or update this repo on the Mac mini.
2. From the repo root, start nginx with the site mounted read-only:

```sh
docker run -d \
  --name mrchl-labs \
  --restart unless-stopped \
  -p 80:80 \
  -v "$PWD":/usr/share/nginx/html:ro \
  nginx:alpine
```

3. Open `http://<mac-mini-ip>/`.

## Updating the site

1. Pull the latest changes into this directory.
2. Restart the container:

```sh
docker restart mrchl-labs
```

## Notes

- The site is fully static: plain HTML and CSS only.
- `/projects/` is served from `projects/index.html`.
- The login form is intentionally non-functional and posts to `/session`, which lets nginx return the static `404.html` page.
