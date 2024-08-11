# archlinux-lcpu 社区源打包者 PGP keyring

这里存放 Arch Linux LCPU 社区源打包者 PGP keyring

## archlinux-lcpu 打包者

如需添加新 key ，请按照以下方式提出 PR ：

1. 将您的 pubkey 提交到某个公开的 keyserver ，确保 `gpg --keyserver --recv-key <fingerprint>` 可接收到您的 pubkey 。
2. 将您的 pubkey fingerprint 填入 master-keyids ，格式为
```
<fingerprint>    <username>    <keyserver>
```
3. 执行：
```bash
updpkgsums
makepkg --printsrcinfo > .SRCINFO
makepkg
```
   * 确保能接收到您的 pubkey ，在 `src/master` 文件夹创建了含有您用户名的 `<username>.asc` 的 pubkey 。
4. 在 commit 中确保 master-keyids 包含了您的 fingerprint，且同时包含对于 `PKGBUILD` 和 `.SRCINFO` 的修改。
