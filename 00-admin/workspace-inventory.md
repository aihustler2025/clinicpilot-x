# Workspace Inventory

Updated: 2026-05-21

## Current Local Findings

### C Drive Workspace

Base path:

`C:\Users\Rosstafari\Documents\New project`

Known project folders:

- `C:\Users\Rosstafari\Documents\New project\FanFlow`
- `C:\Users\Rosstafari\Documents\New project\FanFlow\cloud`
- `C:\Users\Rosstafari\Documents\New project\PRIME10X`
- `C:\Users\Rosstafari\Documents\New project\CLINICPILOTX`

Git findings:

- `FanFlow\cloud` is the actual FanFlow Git repo root.
- `FanFlow\cloud` remote: `https://github.com/aihustler2025/fanflow.git`
- `FanFlow\cloud` branch: `main`
- `PRIME10X` is a Git repo.
- `PRIME10X` remote: `https://github.com/aihustler2025/prime10x-homebase.git`
- `PRIME10X` branch: `main`
- The parent `New project` folder has a `.git` folder but no remote configured.

### D Drive External Workspace

Base path:

`D:\`

Important folders seen:

- `D:\BuzzForge`
- `D:\BUZZOOKA`
- `D:\CLINICPILOT X (Old)`
- `D:\DASHCARDS`
- `D:\PRIME10X`
- `D:\prime10x-homebase`

Git findings:

- `D:\BuzzForge` is a Git repo.
- `D:\BuzzForge` remote: `https://github.com/aihustler2025/BuzzForge`
- `D:\prime10x-homebase` is a Git repo.
- `D:\prime10x-homebase` remote: `https://github.com/aihustler2025/prime10x-homebase.git`
- `D:\DASHCARDS` is not currently a Git repo at the top level.
- `D:\PRIME10X` is not currently a Git repo at the top level.

## Current Mismatch

FanFlow currently lives as an active repo on the C drive:

`C:\Users\Rosstafari\Documents\New project\FanFlow\cloud`

No D-drive FanFlow repo mirror was found during this scan.

CLINICPILOTX was created on the C drive:

`C:\Users\Rosstafari\Documents\New project\CLINICPILOTX`

The D drive already contains:

`D:\CLINICPILOT X (Old)`

## Recommendation

Before development continues, create a clean D-drive project root for active Buzzooka repos. Example:

`D:\BUZZOOKA-WORKSPACE`

Inside it, keep clean Git repo mirrors:

- `D:\BUZZOOKA-WORKSPACE\BuzzForge`
- `D:\BUZZOOKA-WORKSPACE\FanFlow`
- `D:\BUZZOOKA-WORKSPACE\Prime10X`
- `D:\BUZZOOKA-WORKSPACE\Dashcards`
- `D:\BUZZOOKA-WORKSPACE\CLINICPILOTX`

Keep old mixed folders as archive/reference until each project is confirmed safely mirrored.

## Open Questions

- Should `D:\BUZZOOKA` become the main workspace root, or should a new clean `D:\BUZZOOKA-WORKSPACE` folder be created?
- Should FanFlow be cloned fresh from GitHub onto D drive, or copied from the C drive and then verified?
- Which GitHub repo corresponds to Dashcards?
- Which GitHub repo should CLINICPILOTX use?
- Should BuzzForge become the parent workspace repo, or stay its own product/system repo?
