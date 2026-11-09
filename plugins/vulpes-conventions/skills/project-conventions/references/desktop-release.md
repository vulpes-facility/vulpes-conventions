# Desktop release

These rules apply to the desktop stacks in `SKILL.md`, section 4: Electron, Tauri, and egui.\
This file gives the procedure.\
The project selects what to use, and this file does not select it.

## Decisions of the project

1. Before the first release, ask the user each item in this table.\
   Write the answers in `docs/conventions/` ([agent-instructions.md](agent-instructions.md)).
2. Use the answers of the project.\
   Do not select a value for the project.

| Item | Examples of answers |
| --- | --- |
| Target operating systems | macOS, Windows, Linux |
| Distribution | Only to the developers, a direct download, or a store (Mac App Store, Microsoft Store, Flathub) |
| App identifier | A reverse domain name, for example `com.example.notes` |
| Packaging formats | `.dmg` or `.zip` for macOS, NSIS, MSI, or MSIX for Windows, AppImage, `.deb`, `.rpm`, or Flatpak for Linux |
| Signing on Windows | A certificate with a hardware key, a cloud signing service such as Azure Artifact Signing, or the Microsoft Store |
| Update channel | None, GitHub Releases, or a server of the project |
| Packaging and update tool for egui | For example cargo-packager or Velopack |

## Procedure

1. Package and release in CI with the packaging tool of the stack.\
   Use the makers and publishers of Electron Forge, the bundler of Tauri, or the egui tool of the project.\
   Do not release from a developer computer.
2. Build each target operating system on a CI runner of that system.
3. Take the version from the release tag ([git.md](git.md)).
4. Set the app identifier before the first release, and do not change it.\
   A change breaks the data folder, the settings, the signing identity, and the updates.
5. Keep each released version available for download, so that a user can go back after a bad update.

## Signing

These rules apply when the distribution goes past the developers.

1. For macOS outside the Mac App Store, sign with a Developer ID Application certificate and the hardened runtime.\
   Then notarize the app, and staple the ticket to it.
2. For the Mac App Store, sign the app with an Apple Distribution certificate, and turn on the App Sandbox.\
   Sign the installer package with a Mac Installer Distribution certificate.\
   Send the build through App Store Connect.\
   App Review takes the place of notarization.
3. For a direct download on Windows, sign each executable and installer with Authenticode and a timestamp.\
   Also sign an MSI or EXE installer that goes to the Microsoft Store.\
   The Microsoft Store signs an MSIX package itself.
4. The private key of a code signing certificate MUST stay on hardware or in a cloud signing service.
5. When the project has its own Linux package repository, sign the repository with GPG.
6. Keep certificates, keys, and notarization credentials in the CI secret store, a hardware key, or a cloud signing service.\
   Do not put them in the repository.
7. For notarization in CI, use an App Store Connect API key, not an Apple ID password.

## Updates

These rules apply when the project has an update channel.

1. Download each update over HTTPS, and verify its signature before the install.
2. Keep the update signing key, for example the updater key of Tauri, in the CI secret store, with a backup.\
   When the key is lost, installed copies cannot get updates.
3. With Electron on macOS, the app MUST be signed to update itself, because Squirrel.Mac requires it.\
   The Tauri updater verifies its own signature, which is separate from the code signature.
