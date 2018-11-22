To reproduce the bug

```
$ docker run -it --cap-add SYS_PTRACE -v $PWD:/workspace staging.registry.howdoi.website/splatform/rootfs-sle12:1.51.120-f92d5da bash

bash> mkdir dotnet && cf dotnet
bash> wget https://buildpacks.cloudfoundry.org/dependencies/dotnet-sdk/dotnet-sdk.1.1.11.linux-amd64-cflinuxfs2-50cd44e6.tar.xz
bash> tar xvf dotnet-sdk*
bash> cd /workspace
bash> strace -o dotnet.log ./dotnet/dotnet --version
```

Check dotnet.log
