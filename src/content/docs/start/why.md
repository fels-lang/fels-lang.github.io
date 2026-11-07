---
title: Why Fels
description: What Fels is for, and where it stands today.
---

Fels is a language that stays close to the machine, like C, while being harder to get wrong and
small enough to keep in your head. It is built around a few ideas:

- Memory lives in zones, and a zone is freed when its block ends.
- Errors are plain values that you check, not exceptions.
- Code can run while the program compiles.
- One tool builds a project, runs its tests and fetches its packages.

Fels is young, and the language still changes. A few programs written in it:

- Strata, a desktop app for tracking investments, with Dear ImGui and SQLite.
- [A raytracer](https://github.com/fels-lang/fels/tree/main/examples/raytracer): path-traced
  spheres of diffuse, metal and glass.
- [A kernel](https://github.com/fels-lang/fels/tree/main/examples/kernel) that boots in QEMU,
  with no operating system underneath.
- [An asteroids simulation](https://github.com/fels-lang/fels/tree/main/examples/ecs_game) built
  on an entity component system.

## Where it stands

- Windows x64 works from end to end.
- Linux x64 works from end to end too: the compiler runs there and builds static executables.
- There is no macOS support and no formatter yet.
- `-g` gives a program debug info: source lines, functions, parameters and locals with their
  types, in a PDB on Windows and as DWARF on Linux. On Windows it needs the import libraries of
  the Windows SDK for now.
- Programs can run without an operating system, on x86-64 and 64-bit ARM: `--target uefi` makes
  a UEFI application and `--target freestanding` an ELF for a kernel, with interrupt handlers
  as functions.
- The safety checks stay on in release builds: index bounds, null pointers, integer overflow and
  division by zero, unless you ask for `fels build --release-fast`.
- CI runs the compiler's tests on Windows and Linux on every push.

The [known issues](https://github.com/fels-lang/fels/blob/main/KNOWN_ISSUES.md) list what is
still rough, and the [changelog](https://github.com/fels-lang/fels/blob/main/CHANGELOG.md) what
changed in each release.

## Tell me how it went

If you try Fels, I would love to hear about it. Open an
[issue](https://github.com/fels-lang/fels/issues) for a bug, a question or an idea. Small
programs that show a problem help the most.
