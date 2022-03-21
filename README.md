# Next.js multiple environment docker compose example

This is a simple project as an example of a multi-environment docker compose setup for Next.js and the following:

- Typescript
- Tailwind
- Postgres db container
- Dev & Production environments

## How to use it?

### Build the docker image
```bash
docker-compose build
```

### Development
```bash
npm run dev:up
```
This will mount your directory and run `next dev` in the container for 

### Production
```bash
npm run prod:up
```

## Docker compose

The `docker-compose.dev.yml` contains overrides to the `docker-compose.yml` to allow you to run the application in a development environment. The scripts defined in `package.json` will illustrate how this is utilised.

For example you could start the development environment using `docker-compose` directly:

```bash
#Optionally add the -d option if you wish to run in detached mode.
docker-compose -f docker-compose.yml -f docker-compose.dev.yml up
```

## Notes

This application is based on `create-next-app --example with-typescript`. If you wish to you can simply copy the `docker-compose.dev.yml` `docker-compose.yml` and `Dockerfile` files to another project to setup the same environment (perhaps with tweaks for your directory structure).