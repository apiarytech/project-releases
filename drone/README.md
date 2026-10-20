# drone releases

Released builds of **drone** (Mini-SCADA Alarm Dialer), for the units in the
field. This folder holds release files only: no source code.

drone is proprietary software, used only under its commercial licence
([LICENSE.md](LICENSE.md), [NOTICE.md](NOTICE.md)). Anyone may download
these files; running them is governed by the licence and by each unit's
licence from the licence server.

## How units use it

The current release is the **channel**, [channel/](channel/):

- `manifest.json` and `manifest.sig`: the release's files with their
  SHA-256 hashes, signed with the release key;
- `files/<sha256>`: one file per release file, named by its SHA-256. Files
  of earlier releases stay, so a unit halfway through a download finishes.

Units read it at

    https://raw.githubusercontent.com/apiarytech/project-releases/main/drone/channel/

and install only what the release key signed, checking every file. The
key's private half never leaves the owner's offline storage, so the files
here cannot be changed without units refusing them.

Each release is also a GitHub Release tagged `drone-v<version>`, with:

- the release notes: what changed, what was tested, anything a site must
  do;
- `drone-<version>.tar.gz`: the same release in one file, for a site
  without internet access to upload on the unit's Updates page.

How a release gets here: `doc/releases.md` in the private drone repository.
