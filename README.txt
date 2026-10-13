AmneziaVPN 4.8.21.0 — WindowsRouteMonitor route-capture fix

Contents:
- windowsroutemonitor-4.8.21.0.patch: unified patch relative to repository root
- windowsroutemonitor.cpp: patched source file

Changes:
1. Do not clone on-link/connected routes (unspecified next hop) into the VPN interface.
2. Correct GetIpForwardTable2() error handling in updateCapturedRoutes(int).
3. Register an exclusion route before reconciling captured routes, so it is respected immediately.

Scope:
Only client/platforms/windows/daemon/windowsroutemonitor.cpp is changed.
No protocol implementation, server configuration, keys, or MikroTik configuration is changed.

Apply:
From the root of a clean checkout of tag 4.8.21.0, run:
  git apply --check windowsroutemonitor-4.8.21.0.patch
  git apply windowsroutemonitor-4.8.21.0.patch

Status:
Patch application was dry-run checked against the uploaded 4.8.21.0 source file.
The project has NOT been compiled or runtime-tested here. Build and test before replacing the installed client.
