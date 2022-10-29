## build

```shell
$ cd linux-kernel-module-rust/hello-world
$ make
$ insmod helloworld.ko
$ rmmod helloworld
$ dmesg | tail -n 3
[521088.916091] Hello kernel module from rust!
[521174.204889] My message is on the heap!
[521174.204891] Goodbye kernel module from rust!
```

## setting on VSCode

`./.vscode/settings.json`:

```jsonc
{
    "rust-analyzer.cargo.extraEnv": {
        "RUST_TARGET_PATH": "/root/linux-kernel-module-rust"
    },
    "rust-analyzer.cargo.target": "x86_64-linux-kernel-module",
    "rust-analyzer.server.extraEnv": {
        "RA_LOG": "lsp_server=debug",
        "RUST_TARGET_PATH": "/root/linux-kernel-module-rust"
    },
    "rust-analyzer.trace.server": "verbose",
    "rust-analyzer.linkedProjects": [
        "hello-world/Cargo.toml",
        "Cargo.toml"
    ],
}
```
