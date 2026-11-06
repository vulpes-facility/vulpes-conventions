# Mobile release

1. Release iOS, Android, and Flutter apps with Fastlane.\
   Keep the `fastlane/` folder in the app folder.\
   Pin Fastlane with a `Gemfile` and `Gemfile.lock`, and run it with `bundle exec fastlane`.
2. Make three lanes: `test`, `beta` (TestFlight, Google Play internal track), and `release`.
3. Run the lanes in CI.\
   Do not release from a developer computer.
4. Set the build number in CI.\
   Take the version name from the release tag ([git.md](git.md)).
5. Make one flavor or scheme for each environment: Android product flavors, Flutter flavors, and iOS schemes.

- Sign iOS apps with `match`.\
  Keep the certificates encrypted in a private store.\
  In CI, run `setup_ci` and use `match` in read-only mode.
- Use Play App Signing.\
  Keep the upload key in the CI secret store.
- Keep the App Store Connect API key and the Google Play service account key in the CI secret store.\
  Do not put them in the repository.
