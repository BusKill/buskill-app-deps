# buskill-app-deps

This repo contains the dependencies required to build the BusKill App.

Unfortunately this app requires some dependencies that are not cryptographically signed, and therefore are not safe to download at the time that the app is being built.

We try to work with upstream devs to sign their releases. But for the dependencies that are not signed, we download them from multiple exits over multiple days (3TOFU), add them to this repo, and then sign them oursevles.

For more info, see:

 * https://github.com/BusKill/buskill-app/issues/2
 * https://github.com/BusKill/buskill-app/issues/78
 * https://github.com/BusKill/buskill-app/issues/24
