> ⚠️ This repository is a fork of the [original project](https://github.com/isar-community/isar-community), focusing primarily on bug fixes and small updates for version 3. Our objective is to enhance the stability and reliability of the codebase while implementing minor improvements to refine the user experience. See details below on how to use this community fork.

---

## Linux Compatibility Fork (glibc < 2.38)

The upstream `isar_community_flutter_libs` (3.3.x) ships Linux binaries that require **glibc 2.38+**. Many common Linux distros ship with an older glibc and will hit this error at runtime:

```
version `GLIBC_2.3x' not found
```

| Distro | glibc | Upstream |
|---|---|---|
| Debian 11 (Bullseye) | 2.31 | ❌ Fails |
| Debian 12 (Bookworm) | 2.36 | ❌ Fails |
| Ubuntu 20.04 LTS | 2.31 | ❌ Fails |
| Ubuntu 22.04 LTS | 2.35 | ❌ Fails |
| Ubuntu 24.04 LTS | 2.39 | ✅ Works |
| Debian 13 (Trixie) | 2.40 | ✅ Works |

This fork rebuilds the Linux native library targeting **glibc 2.28**, covering all distros above. Only `isar_community_flutter_libs` is patched — all other packages remain from upstream.

To use this fix, add a `dependency_overrides` in your `pubspec.yaml`:

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