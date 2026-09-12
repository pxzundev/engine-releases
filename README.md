# engine-releases

Binary release channel for the Writer app bundled llama.cpp engine.

- One GitHub Release per llama.cpp version (tag = llama.cpp build, e.g. `b10930`).
- Assets are named `engine-<platform-key>.zip`; platform keys match
  `installable_platform_keys()` in the app (macos-aarch64, windows-x86_64[-cuda|-vulkan|-cpu]).
- macOS assets are the official llama.cpp tar.gz builds repacked as zip; Windows assets are the
  official zips renamed. MIT-licensed redistribution.
- `manifest.json` on main is the contract: the app refuses any asset whose sha256 differs
  from the manifest. Bump `version` only after every asset of that version is uploaded;
  never replace assets of a version the manifest already advertises.
