# MRCHL Labs

MRCHL Labs is a static website for the studio's public homepage and projects page.

## Static site

- Plain HTML and CSS only
- No framework
- No build step
- No JavaScript dependencies

## Deployment

The site is deployed from:

`/mnt/stockage/docker/mrchl-labs`

It is intended to be served by an nginx Docker container mounting this directory as the web root.

## Update workflow

```sh
git pull origin main
```
