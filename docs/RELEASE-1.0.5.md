# MPS 1.0.5 — release notes

MPS 1.0.5 is available for Windows x64, Ubuntu 24.04 and 26.04 x64, and the umbrelOS community store (AMD64/ARM64). Upgrade a managed 1.0.4 installation in place; do not uninstall first. Back up the entire data directory, including the database, configuration and encryption key.

## Features and improvements

- Eligible members can invite up to three family members using reusable places. An administrator enables invitations; family access follows the sponsor's active membership and verified Emby/Jellyfin permissions. Invitations can be retracted. Offline setup is retried and its progress is shown to the member.
- Administrators can confirm removal of an Emby or Jellyfin server. It disappears from new assignments immediately; linked accounts are disabled on the remote server with identity checks and retry status if the server is offline. Other servers and their assignments remain intact.
- Administrators can see the current MPS release status and check for updates manually. Background checks use bounded, product-specific metadata from the MPS website. They never install an update; Umbrel updates remain in the community store.
- Membership details appear before server links. Request history remains under Discover & request. Fixed application purchase prices are removed from shipped help in favour of the current MPS website pricing; member plans and existing subscription contracts are unchanged.

## Fixes

- Request availability can now show verified Emby, Jellyfin or both. One provider's outage does not hide a separately confirmed location; unverified checks retry.
- Eligible linked imported Emby accounts regain their **Open Emby** link without bypassing managed-disable precedence or showing another member's servers.

- Family revocation and server removal disable Live TV as well as account access on remote Emby and Jellyfin servers.

## Upgrade and distribution

Schema v2 migrates to v3 by adding family and server-removal records. Older managed schema v1 installations migrate through v2. Existing provider and server records are retained. Rolling back requires both the old package and its matching pre-upgrade data backup.

Windows and Ubuntu installers are available from the [official MPS downloads page](https://mediapaymentsystem.app/downloads), not GitHub release assets. The Umbrel community store remains the distribution path for its app. The published installers passed checksums, compiled-source exclusion, installed-package and upgrade tests.

The Windows installer remains unsigned. The Ubuntu 24.04 installer requires systemd and Python 3.12; the separate Ubuntu 26.04 installer requires systemd and Python 3.14. The default Umbrel proxy protects its preview; public invitations and payment callbacks still need a separately verified public HTTPS deployment.
