# learn-http-odin

Implement an http server from scratch using syscalls. Written in Odin and the implementation is specific to MacOS. Avoid using the Odin stdlib syscall wrappers.

## Quickstart

```
bin/darwin/lua bootstrap.lua

bin/darwin/lua odin run src/tcp.odin -file
nc -E 127.0.0.1:<port>

bin/darwin/lua odin run src/http.odin -file
curl --include 127.0.0.1:<port>
curl --include 127.0.0.1:<port>/wazoo
curl --include 127.0.0.1:<port>/my-super-secret-page
# Lastly, visit in your browser: 127.0.0.1:<port>/my-super-secret-page

```

## List libc macro definitions (MacOS):

`$ cd "$(xcrun --show-sdk-path)/usr/include/sys/types.h`

```
clang -E -dM "$(xcrun --show-sdk-path)/usr/include/sys/socket.h  | $EDITOR"
clang -E -dM "$(xcrun --show-sdk-path)/usr/include/sys/types.h   | $EDITOR"
clang -E -dM "$(xcrun --show-sdk-path)/usr/include/netinet/in.h  | $EDITOR"
```

## Syscall stdlib wrappers:

```
core:net
core:sys/darwin/sys_socket.odin
core:sys/posix/*
```

