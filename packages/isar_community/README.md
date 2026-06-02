> ⚠️ This repository is a fork of the [original project](https://github.com/isar-community/isar-community), focusing primarily on bug fixes and small updates for version 3. Our objective is to enhance the stability and reliability of the codebase while implementing minor improvements to refine the user experience. See details below on how to use this community fork.

---

## Linux / Debian 11 Compatibility Fork

This fork fixes a `GLIBC not found` error on **Debian 11 (Bullseye)** and other systems with older glibc (< 2.36). The upstream `isar_community_flutter_libs` ships binaries built for newer glibc (Debian 13+), which crash on Debian 11 at runtime.

Only `isar_community_flutter_libs` is patched here — all other packages remain from upstream. To use this fix, add a `dependency_overrides` in your `pubspec.yaml`:

```yaml
dependency_overrides:
  isar_community_flutter_libs:
    git:
      url: https://github.com/cas8398/isar-community.git
      path: packages/isar_community_flutter_libs
```

This override applies **only to Linux**. Android, iOS, macOS, and Windows are unaffected and continue to use the upstream binaries.

For the full quickstart, documentation, and examples, refer to the [upstream repository](https://github.com/isar-community/isar-community).

---

### License

```
Copyright 2022 Simon Leier

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
