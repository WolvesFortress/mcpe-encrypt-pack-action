# mcpe-encrypt-pack-action
GitHub action for encrypting resource packs. Automatically creates a .mcpack and .key in releases
# Usage
In your workflow file add this to your steps:

```yml
uses: WolvesFortress/mcpe-encrypt-pack-action@v1.0.0-alpha
```

To build and release your pack, add `[release]` to your commit message. This will trigger the action and create a release with the encrypted `<reponame>.mcpack` and `<reponame>.key` under the same version as in the pack's `manifest.json`.

## ⚠ Important notice
Your pack's version ***must*** be different every time you push a release. The Minecraft client caches resource packs. Each time the manifest's version or UUID change, the client will download a new version of the pack. If you update your encrypted pack but do not change the version, the decryption will use the cached version, not decrypt or disable the pack. This is also why i decided to use the `[release]` tag detection, so the pack won't suddenly break. Just.. bump your versions, okay?
