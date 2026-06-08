# buskill-app-deps

This repo contains the dependencies required to build the BusKill App.

Unfortunately this app requires some dependencies that are not cryptographically signed, and therefore are not safe to download at the time that the app is being built.

We try to work with upstream devs to sign their releases. But for the dependencies that are not signed, we download them from multiple exits over multiple days (3TOFU), add them to this repo, and then sign them oursevles.

For more info, see:

 * https://github.com/BusKill/buskill-app/issues/2
 * https://github.com/BusKill/buskill-app/issues/78
 * https://github.com/BusKill/buskill-app/issues/24

# Resign Instructions

After you update the contents of the `build/deps/` directory, you can run the following commands to update the `SHA256SUSM` digest file and its detached signature file `SHA256SUMS.asc`

```
cd buskill-app-deps/build/deps
sha256sum * > SHA256SUMS
sed -i '/SHA256SUMS/d' SHA256SUMS
sed -i '/download.sh/d' SHA256SUMS
gpg --default-key 'E0AF FF57 DC00 FBE0 5635  8761 4AE2 1E19 36CE 786A' --textmode --armor -b SHA256SUMS
```
