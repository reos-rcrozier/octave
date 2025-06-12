Here is your `AGENTS.md` file for guiding an OpenAI Codex agent to build and test the GNU Octave project from its sources. The formatting is provided below **as plain text** (not rendered markdown) so you can copy and use it directly.

---

```markdown
# AGENTS.md

## Purpose

This document provides step-by-step instructions for building the GNU Octave project from its source code using an automake-based workflow. These instructions are intended for use by an automated agent or human developer working from a clean repository checkout. **This guide does not cover installation of prerequisites.**

## Build Instructions

1. **Clone or Checkout the Repository**

   Ensure you have a clean copy of the GNU Octave source tree. This may be from a mercurial clone, a git checkout of the official git mirror of the hg repository.

2. **Prepare the Build System**

   Run the provided `bootstrap` script in the root of the repository. This step only needs to be performed once per clean source tree.

   ```sh
   ./bootstrap
   ```

   This script generates all necessary build configuration files.

3. **Configure the Build**

   Configure the build system. For a build without the GUI, use the following command:

   ```sh
   ./configure --without-qt
   ```

   This will set up the build to exclude any Qt-based graphical user interface components.

4. **Compile the Project**

   Compile the source code using `make`:

   ```sh
   make
   ```

   This will build the entire project according to the specified configuration.

5. **Run the Tests**

   After building, execute the test suite to verify the build:

   ```sh
   make check
   ```

   This runs the project's built-in tests to ensure correctness.

## Notes

- Steps above assume all build dependencies and prerequisites are already installed.
- For repeated builds after small changes, only the `make` and `make check` steps are necessary.
- If the build tree is cleaned or the repository is re-cloned, start again from step 2.

```

---
