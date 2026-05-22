# GitHub Repo Creation Instructions

Target repo name:

`clinicpilot-x`

Suggested owner:

`aihustler2025`

Suggested visibility:

Private until the product is ready.

Suggested description:

`ClinicPilot X - Buzzooka-owned lead intake and automation product for clinics, med spas, dental practices, salons, and service businesses.`

Local repo path:

`D:\BUZZOOKA WORKSPACE\Products\ClinicPilot X`

Manual browser path if Codex cannot control GitHub directly:

1. Open `https://github.com/new`.
2. Repository name: `clinicpilot-x`.
3. Visibility: Private.
4. Do not initialize with README, `.gitignore`, or license because the local repo already has files.
5. Create repository.
6. Send Codex the new repo URL.

After the repo exists, Codex should run:

```powershell
git -c safe.directory="D:/BUZZOOKA WORKSPACE/Products/ClinicPilot X" remote add origin https://github.com/aihustler2025/clinicpilot-x.git
git -c safe.directory="D:/BUZZOOKA WORKSPACE/Products/ClinicPilot X" add .
git -c safe.directory="D:/BUZZOOKA WORKSPACE/Products/ClinicPilot X" commit -m "Initialize ClinicPilot X project memory"
git -c safe.directory="D:/BUZZOOKA WORKSPACE/Products/ClinicPilot X" push -u origin main
```
