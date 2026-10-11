# FS25 Native VR — prototype foundation

This is **not yet an independent, proven replacement**. It is a source-based experimental foundation derived from the MIT-licensed FS25VR project (original copyright and notices preserved), with the user's latest `xr.cpp` and an automated Windows build workflow. It exists to make repeatable builds possible **without installing Visual Studio locally**.

## Build on GitHub
1. Create a new **private** GitHub repository and upload the **contents** of this folder (including `.github/workflows/build-windows.yml`).
2. In GitHub open **Actions** → **Build Windows VR prototype** → **Run workflow**.
3. After a successful run, download `FS25-NativeVR-Windows-prototype` from the workflow's **Artifacts** section.
4. Keep the current working DLL backed up. Do **not** install this experimental build until the workflow succeeds and we have reviewed its output.

## Next engineering milestone
Implement a controlled static stereo test scene, log actual image-to-pose association and compare the two captured eye images against submitted OpenXR pose/FOV. Only then replace alternating-frame rendering with same-simulation-frame paired rendering if engine hooks permit it.

## Limitations
The project currently inherits FS25VR's alternate-eye renderer, including its stereo-alignment issue. This package does not claim to fix it. It does not include a compiled DLL. CI requires GitHub-hosted Windows runners and network dependency downloads. The first CI build may expose compiler or package compatibility errors that require corrections.
