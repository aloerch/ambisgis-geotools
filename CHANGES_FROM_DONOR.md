# Owned changes after the retained GeoTools baseline

## Per-module source identity — PLT-01, 2026-10-04

Predecessor: 3363c3d4ae8adfe3ed2024c27f92ec63855093be
(tree ebb65f687763ce40445eb02f6ce710dc1eaa1e00). Existing history,
copyright and license notices remain unchanged.

The owned aggregate builds several source repositories in one Maven reactor.
The parent POM now disables reactor-wide Git-property injection and defaults
to resolving Git metadata for each module. This prevents GeoTools from
broadcasting its Git identity into the other owned roots.

The build producer must supply genuine metadata for each selected owned Git
revision and verify embedded revisions after building. These POM settings alone
do not prevent discovery of an unrelated ancestor repository in a plain source
export. They change build provenance behavior, not GIS algorithms. Native build,
artifact identity and installation acceptance require their separate evidence.
