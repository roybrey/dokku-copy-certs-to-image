# dokku-copy-certs-to-image

Copies certs from the host's `/home/dokku/<APP>/tls` directory to the `/app` directory of a dokku image before the image is released.

Only affects deploys where buildpacks are in use. Files are not available during the build step.

## requirements

- dokku 0.4.0+
- docker 1.6.x

## installation

```shell
# on 0.4.x
dokku plugin:install https://github.com/dokku/dokku-copy-files-to-image.git  copy-files-to-image
```

## usage

A deploy should automatically add the certs to the `/app` directory of the image, and the files will be available during container runs.

### caveats

- Does not copy directories or directory structures
- Does not copy files prefixed by periods
- Will not persist mode on copied files
