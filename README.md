# Members Portal Preview Store

Community test distribution only — not an official Umbrel App Store release.

## Install
1. In umbrelOS, open **App Store → Community App Stores** (usually in the
   App Store menu).
2. Add `https://github.com/matty03072/members-portal-preview-store`.
3. Open **Members Portal Preview** and install **Members Portal (Preview)**.
4. Open the installed app from Umbrel. Unlock first-run setup with username
   `owner` and the app password shown by Umbrel.
5. Create your permanent owner account and enrol MFA with an authenticator.

Requires the container package to be public before installation. If installation
reports a GHCR access-denied error, the publisher must finish package visibility
setup; no registry password should be required on Umbrel.

## Isolation and limitations
App ID: `memberspreview-members-portal`. Port: `18099` (must be unused).
Data is separate from any future official app. No live-site configuration,
production database, credentials or member records are included.

Use test integrations only. Default Umbrel authentication protects every route;
public invitations and external payment callbacks are not supported by this
preview configuration. No official-store submission has been made.

Source and build checks: https://github.com/matty03072/members-portal-preview

Container checks do not constitute an umbrelOS installation test. The first
install, UI setup/MFA, reboot and backup/restore still need testing on your Umbrel.
Back up the entire app data folder, including its configuration and encryption
key. Do not assume automatic migration to a future production app ID.

The public store and container are accessible to other people; community/test
means outside the official store, not private distribution.
