# ApiaryTech releases

Released builds of ApiaryTech's commercial products: the compiled programs
and firmware from the private repositories, never their source code. One
folder per product.

| Folder | Product | What a unit reads |
|---|---|---|
| [drone/](drone/) | drone, Mini-SCADA Alarm Dialer (Linux field unit) | `drone/channel/` |
| [dronebuzz/](dronebuzz/) | drone-buzz, the ESP32 tier of drone | firmware images in its GitHub Releases; no over-the-air channel yet |

## How it works

- A product's **channel** is a folder of this repository on `main`:
  `manifest.json`, `manifest.sig` and `files/<sha256>`, one file per
  release file, named by its SHA-256. Units read it as raw files,

      https://raw.githubusercontent.com/apiarytech/project-releases/main/<product>/channel/

  and install only what the product's release key signed, checking every
  file. The key's private half never leaves the owner's offline storage, so
  the files here cannot be changed without units refusing them. Whatever
  `main` holds is the current release; `git log` is the history.
- Each release is also a **GitHub Release**, tagged `<product>-v<version>`
  (for example `drone-v1.3.0`), with the release notes and the one-file
  package for a site without internet access. No release is marked
  *latest*: the repository holds several products.
- The licence is in each product's folder (`LICENSE.md`, `NOTICE.md`).
  Anyone may download these files; running the software is governed by the
  licence.

How a release gets here is described in each private repository
(`doc/releases.md` in drone).
