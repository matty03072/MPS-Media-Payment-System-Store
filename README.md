# MPS — Media Payment System

Community Preview Store

Community test distribution only — not an official Umbrel App Store release.

## What is MPS?

MPS brings media memberships, payments and connected service accounts into one self-hosted portal. It integrates **Emby, Emby Connect, Ombi, Stripe, PayPal and SMTP email** so administrators can manage invitations, plans, permissions and member access together.

After services are configured and an invited member signs up and verifies their email, MPS can automatically create their **Emby server accounts**, register or authenticate and link **Emby Connect**, and create or link their **Ombi account** using the signup details. The background worker tracks progress, retries recoverable failures and flags account conflicts. Access depends on membership entitlement, and Emby Connect may require its own email verification.

Members can manage their membership, open Emby and discover/request content through Ombi from the same portal. MPS coordinates the services; it does not replace them or automatically configure the administrator's service connections.

Read the [full application overview and automation workflow](https://github.com/matty03072/MPS-Media-Payment-System#automated-account-creation), including the default preview's public-access and payment-callback limitations.

## Custom branding

Administrators can open **Configuration → Branding** to upload their logo and set their own site name. The site and new emails use the saved branding, with a linked MPS — Media Payment System credit retained in the footer.

![Branding settings](https://raw.githubusercontent.com/matty03072/MPS-Media-Payment-System/88a980b778f17858f147c98e0e09bb3073a637b8/docs/screenshots/branding-settings.png)

## Screenshots

Live application views with temporary MPS branding; names and emails removed before blurring. No live-site data or configuration is included in the install.

### Administrator overview

![MPS administrator overview](https://raw.githubusercontent.com/matty03072/MPS-Media-Payment-System/bd5d8035ab55c8f5cccd6db39d0d704b1474beb9/docs/screenshots/admin-overview.png)

### Member dashboard

![MPS member dashboard](https://raw.githubusercontent.com/matty03072/MPS-Media-Payment-System/bd5d8035ab55c8f5cccd6db39d0d704b1474beb9/docs/screenshots/member-dashboard.png)

### Member request statuses

![MPS member request statuses](https://raw.githubusercontent.com/matty03072/MPS-Media-Payment-System/44994dfc2fd1fa7b1734ef5b0bbf7580a848de84/docs/screenshots/member-request-status-redacted-v2.png)

## Install
1. In umbrelOS, open **App Store → Community App Stores** (usually in the
   App Store menu).
2. Add `https://github.com/matty03072/MPS-Media-Payment-System-Store`.
3. Open **MPS — Media Payment System** and install **MPS — Media Payment System**.
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

Source and build checks: https://github.com/matty03072/MPS-Media-Payment-System

Container checks do not constitute an umbrelOS installation test. The first
install, UI setup/MFA, reboot and backup/restore still need testing on your Umbrel.
Back up the entire app data folder, including its configuration and encryption
key. Do not assume automatic migration to a future production app ID.

The public store and container are accessible to other people; community/test
means outside the official store, not private distribution.

## Branding update (beta.3)
New MPS logo and identity across the app, emails and listing. Use Umbrel Update
for the existing app; do not uninstall. The stable app ID and repository URL are
retained to preserve update continuity and data. Sign in again after updating.

## Current features (beta.4)

The preview now includes Sonarr/Radarr connection settings, member-scoped download
and import progress, optional post-import Emby scans, separate configuration pages
and Emby server editing/library refresh. Configure your own services under
**Configuration → Connected services**; no live-site credentials are included.
Update the existing app in place. No schema migration is needed.
