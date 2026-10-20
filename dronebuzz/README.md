# drone-buzz releases

Firmware images of **drone-buzz**, the ESP32 tier of drone: alarms in,
callouts out by SMS and email, on an ESP32-S3 with a cellular module. This
folder holds released firmware only: no source code.

drone-buzz is proprietary software, on the same terms as drone
([../drone/LICENSE.md](../drone/LICENSE.md)).

## How a board gets it

Each release is a GitHub Release tagged `dronebuzz-v<version>`, with the
firmware image(s) for the supported board(s) and the release notes. A board
is flashed by cable, as the private repository's scripts describe; there
are no over-the-air updates yet, so this folder has no channel. When there
are, the channel will be `dronebuzz/channel/`, laid out like drone's.
