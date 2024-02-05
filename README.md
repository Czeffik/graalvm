# MacOS with aarch64

If you are working on macbook with `aarch64` architecture and you would like to build native image
using [GraalVM](https://www.graalvm.org/latest/docs/getting-started/macos/) it may be necessary to use 
[Docker](https://www.docker.com/get-started/) with `Use Rosetta for x86/amd64 emulation on Apple Silicon` feature enabled.



Run this command in your GraalVM project directory

```shell
docker run --rm -it -v $(pwd):/app --platform linux/amd64 --entrypoint /bin/bash ghcr.io/graalvm/native-image-community:21
```

Where:
- `--rm` - docker deamon [will remove this container after you are done](https://stackoverflow.com/a/49726371)
- `-it` -  connect straight to container
- `-v $(pwd):/app` - mounts your current directory as volume in docker container
- `--platform linux/amd64` - select target native image platform
- `--entrypoint /bin/bash` 

