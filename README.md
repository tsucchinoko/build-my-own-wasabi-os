# 作って学ぶOSの仕組み


## Command

- ビルド

```zsh
cargo build --target x86_64-unknown-uefi
```

- バイナリのコピー

```zsh
cp target/x86_64-unknown-uefi/debug/wasabi.efi mnt/EFI/BOOT/BOOTX64.EFI
```

- QEMU経由でのBIOSとして仮想マシンを起動

```zsh
qemu-system-x86_64 -bios third_party/ovmf/RELEASEX64_OVMF.fd -drive format=raw,file=fat:rw:mnt
```
