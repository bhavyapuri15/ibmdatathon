# Submission checklist

Accuracy-review update: see [JUDGING_GUIDE.md](JUDGING_GUIDE.md) and [ACCURACY_REVIEW.md](ACCURACY_REVIEW.md). Checked items below describe the earlier deployment, not automatic approval of revised source. Re-run the final tests/evidence and capture fresh screenshots before recording. New experiments remain explicitly experimental; the default baseline is preserved.

Status as of 2026-10-17 ~17:10 SGT. [x] = done and verified, [ ] = team action needed.

## Build and evidence

- [x] Full pipeline executed on LinuxONE (s390x): train → evaluate → validate-physics → benchmark-planner → benchmark-runtime (`artifacts/linuxone/pipeline/status.log`).
- [x] 26/26 tests pass on both macOS arm64 and LinuxONE s390x.
- [x] OrbitGuard systemd service is active on the VM, bound to 127.0.0.1:8000, enabled at boot.
- [x] Live browser smoke test passes through the SSH tunnel, including a real screening job and evidence rendering (`frontend/test-results/live-*.png`).
- [x] `docs/RESULTS.md` is generated from LinuxONE artifacts.

## Required by the guidebook (team)

- [x] Complete both prerequisite labs: the churn (Lab 1) and loan-approval (Lab 2) notebooks from https://github.com/linuxone-community-cloud/jupyter-lab-ml ran on LinuxONE on 2026-10-17. Executed notebooks and screenshots are in `docs/labs/`. Confirm on Discord that these are the two labs meant by the guidebook.
- [ ] Create the GitHub repository (public, or private with judge access) and push. Before pushing, run `git status` and confirm that `key.pem`, `artifacts/` and `.venv/` are **not** staged (`.gitignore` covers them).
- [ ] Record the ≤ 3-minute video following `docs/DEMO_SCRIPT.md`. Check the duration before uploading.
- [ ] Capture LinuxONE evidence screenshots:
  - a terminal showing `uname -m` → `s390x`
  - `systemctl status orbitguard`
  - `cat artifacts/pipeline/status.log`
  - the dashboard header's "IBM LinuxONE s390x" status indicator
- [ ] Fill in the submission form: repo link, video link, team name **Datathon2**, short description (use the README's first paragraph).
- [ ] Submit with ≥ 30 min buffer for upload failures.

## Do not

- Do not commit or share `key.pem` or the ESA label file.
- Do not quote numbers that are not in `docs/RESULTS.md`.
