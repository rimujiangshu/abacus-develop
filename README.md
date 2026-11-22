# Isolated ASE verification for PR 8359

This is a CI-only orphan branch in the personal fork. Do not merge it into any
source branch. It intentionally contains no ABACUS source and no unrelated
workflows.

The sole workflow runs on pushes to this named branch. One verification run
is authorized; do not push again to retry automatically. It checks out
the unchanged source commit `bf34603d1a1487a6de8faf25bde4e3a43c6d404b`, uses the
original failed CI container digest, and runs the original ASE unit and
integration scripts with unchanged assertions and inputs.

Only the workflow trigger/isolation, pinned checkout/image, and evidence
collection differ from the upstream ASE workflow. The original build flags,
dependency installation recipe and tests are retained. Scripts are invoked
with Bash instead of changing their executable permission bits.

No default branch or PR source branch is updated. No upstream PR is created,
updated, or commented on. No SSH, HPC scheduler, self-hosted runner, GPU job,
release, package publication, mirror, or deployment is used. Artifacts contain
only this public-source CI run, not private scientific logs or datasets.

A successful fork run is independent verification evidence. It does not
replace the failed upstream check or prove that upstream issue #7794 is fixed.
