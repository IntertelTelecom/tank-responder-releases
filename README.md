# tank-responder releases

Signed release files of **tank-responder**, Intertel Telecom's internal tool for answering
Tank 2.0 identification requests. This repository holds only the downloads; the source code
is private.

## Install

Download the newest release under **Releases**:

- **Windows:** `tank-responder-setup.exe`
- **macOS (Apple silicon):** `tank-responder-macos.zip`, unzip it and move `tank-responder.app`
  to Applications. The first time, right-click → Open → Open ("Open Anyway").

After that, the app updates itself: when a newer version is out it shows **Update available**,
and installs it when you click **Update now**.

## How updates are verified

Each release includes `latest.json` (version, and for each download its address, SHA-256 hash
and size) and `latest.json.sig`, an Ed25519 signature of that file. The app has Intertel
Telecom's public key built in. It installs an update only when:

- the signature matches that key;
- the version is newer than the installed one;
- the download's hash and size match the signed file.

The private key is never stored here, so changing the files in this repository can't produce
an update the app accepts.
