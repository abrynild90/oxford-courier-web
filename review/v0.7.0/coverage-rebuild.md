# Rebuilding the fidelity audit

Build the release Blender assets and finish writing the street manifest first. Then run from the repository root.

```sh
blender -b -t 4 --python-exit-code 4 --python tools/blender/precinct_fidelity_audit.py -- --tag v0.7.0
```

The command opens the editable scenes without writing to them. It writes `coverage.html` and `coverage.json` in this directory. Pass `--output` after the Blender separator to change the destination. The HTML embeds the audit data, so its inventory remains usable in a browser without network access. External references, editable source links, and runtime assets use the published version URLs. Editable files require access to the private source repository.

The audit compares tile index, source ID and anchor before checking the registered mesh and GLB. It verifies the supplied GLB digest where the runtime manifest provides one. Run the game’s district smoke tests separately to verify streaming, browser rendering and collision behavior. Plan and roof measurements retain the scope and dates of the frozen source ledgers.
