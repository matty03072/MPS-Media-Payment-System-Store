# MPS 1.0.4 — release notes

## Current subscription pricing

From 27 October 2026, new MPS unlock subscriptions cost **£10 per month** for
up to three applications. The ten-member free tier is unchanged. Existing
subscriptions retain their agreed price. The 1.0.4 installers may display the
previous price; the current price and terms are shown before purchase at
https://mediapaymentsystem.app/mps.

MPS 1.0.4 is a **new release** for Windows x64, Ubuntu 24.04 x64 and the
umbrelOS community preview (AMD64/ARM64). New users install the 1.0.4 package.
Owners of managed MPS 1.0.3 installations update **in place**: keep the same
app identity and data directory, and run the new installer or use Umbrel's
**Update** action. Do not uninstall to update. Back up the entire data directory,
including the database, configuration and encryption key, first.

## Download checksums (SHA-256)

```text
c1701d0ba7fc115737c754acafe579c0e6bcb41d121bc960acc06373f15c134a  MPS-1.0.4-linux-x64.tar.gz
4826db1208948223cb25c2e0706146020d99e884a563fd1a0f33822ddf1667a1  MPS-1.0.4-windows-x64-setup.exe
```

The same values are in the `SHA256SUMS.txt` release asset. Download only the
1.0.4 installers from the current release page; older installer assets have
been retired from the public Store release.

The umbrelOS community package pins both services to the multiarchitecture
`v1.0.4` index digest
`sha256:d5ed3fb21a69048650c036fa968ced1914c1c996c8d77a7ea334d037f53a7785`.

## New in 1.0.4

- Jellyfin joins Emby as a selectable media-server provider. Administrators can
  configure multiple servers, choose libraries and Live TV permissions for an
  invitation, and add Jellyfin access to an existing managed member. Jellyfin
  accounts are local to each server; a Jellyfin-only invitation does not use
  Emby Connect. Member launch links show only assigned servers.
- Sonarr and Radarr have separate Configuration pages. Request-progress settings
  move to System information. The old combined settings URL redirects.
- The optional Media Managers area exposes Ombi Approvals, Radarr and Sonarr
  administration when the relevant service is enabled and connected. Members
  do not gain these administrator controls.
- Member and administrator built-in guides cover the new server and manager
  workflows without the beta site's MPS administration tab.

## Upgrade and compatibility

The 1.0.4 database migration adds provider metadata without reclassifying
existing Emby servers. Existing settings, account identifiers and entitlement
records remain in the managed data directory. A 1.0.3 binary cannot read the
newer schema: rollback means restoring the matching **1.0.3 data backup** as
well as its package. Do not point an old binary at migrated 1.0.4 data.

The Windows installer remains unsigned. Linux requires systemd and CPython
3.12. Default Umbrel authentication protects the community preview; public
invitations and external payment callbacks still require a separately secured
public HTTPS deployment. The community preview is not an official Umbrel App
Store release.

Only compiled first-party application modules are distributed in the Windows,
Linux and container runtimes; the application source remains private.

## Verification scope

Windows and Ubuntu candidates were installed on disposable native CI runners,
with service/worker start, repair, restart, uninstall-with-data-preserved,
compiled-payload tests and a real upgrade from the released 1.0.3-r2 packages.
AMD64 and ARM64 container candidates passed runtime/source-layer audits and a
1.0.3-image to 1.0.4-image upgrade using the same persistent `/state` volume.
The beta Jellyfin server accepted a disposable user creation, restricted
library policy, password login and deletion. Portal-driven Jellyfin lifecycle
tests used isolated fake providers; a live portal-linked member lifecycle,
Live TV playback, external SQL Server/PostgreSQL upgrade and an actual on-device
umbrelOS update have not been verified. Test a disposable member and take a
full data backup before relying on a new integration in your environment.
