# Client apps

| Item | Web (React, Vue) | Flutter | Android (Kotlin) | iOS (Swift) |
| --- | --- | --- | --- | --- |
| Architecture | Feature-Sliced Design: `app`, `pages`, `widgets`, `features`, `entities`, `shared` | Flutter app architecture guide | Android guide to app architecture | The same layers as Android |
| Layers | Slices and segments | UI (views, view models), data (repositories, services), domain when large | UI (Compose, ViewModels), data (repositories, data sources), domain when large | UI (SwiftUI, view models), data, domain when large |
| Layer check | steiger | A test that reads the imports | Gradle modules, and a test of the module graph | Swift Package Manager targets, and a test of the package graph |
| Server data | TanStack Query | Repositories | Repositories | Repositories |
| Shared state | zustand (React), Pinia (Vue) | View models | ViewModels | View models |
| Parse answers | zod or a similar schema | `json_serializable` | `kotlinx.serialization` | `Codable` |
| Build-time values | `VITE_` variables | `--dart-define` | `BuildConfig` | `.xcconfig` |
| Local database | IndexedDB | drift or sqflite | Room | SwiftData or Core Data |
| End-to-end tests | Playwright | `integration_test` | Compose UI tests | XCUITest |

1. Send all API calls through one client module.\
   Parse each value that comes into the app: API answers, storage, and the address.
2. Build-time values are public.\
   Do not put secrets in them.
3. When one web image goes to many environments, serve the runtime values in a file from the web server.
4. Load each page or route when the user opens it.
5. Make the layer rules part of the build.\
   Gradle modules and Swift packages refuse an import that they do not declare.\
   A test of the module graph refuses a dependency that points outward.
6. When an app keeps a local database, write each schema change as a migration.\
   Do a test of the upgrade from the last released version.

- Keep code in the slice or feature that uses it.\
  When a second one uses it, move it down a layer.
- Make screens with one component library and design tokens, not raw colors.\
  On the web, use Tailwind CSS.\
  Do not write stylesheets by hand.
- When the React Compiler compiles a component, do not add `useMemo`, `useCallback`, or `memo` to it for speed.
- Use effects and watchers only to synchronize with systems outside the framework: timers, global keys, device APIs, and DOM APIs.
- Get server data through the query cache or a repository, not in an effect.
- In tests, find elements by role, by label, or by a test key.\
  Do not find them by class or by position.
- Each new user flow MUST get an end-to-end test step.
