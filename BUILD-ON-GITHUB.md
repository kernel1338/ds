# Build Donut Payments for Fabric 1.21.11

1. Create a new GitHub repository.
2. Upload the *contents* of this folder to the repository root (including `.github/workflows/build.yml`). GitHub's web uploader may hide dotfolders on some systems; use git or drag the files with hidden files enabled.
3. Open the repository's **Actions** tab, select **Build Fabric mod**, then **Run workflow**.
4. When the build succeeds, open its run and download the artifact named `donut-payments-fabric-1.21.11`.
5. Extract the artifact ZIP. Install the normal remapped mod JAR (not `-sources.jar`) in your Fabric mods folder. Install matching Fabric API as needed.

If the build fails, copy the log from **Compile mod** and send it here. This is a build workflow, not proof the project compiles. The current source may need Minecraft 1.21.11 API corrections.
