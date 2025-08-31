# Neo-Pāramitā

*Forked from https://github.com/3TUSK/Paramita*

> When you still can't decide which loader and which version to develop with... why not choose *ALL OF THEM*?

This is a multi-project template for those who wish to develop a single Minecraft mod on multiple Minecraft versions ~~and 
multiple loaders~~ (forge/neoforge only), altogether in a single place. 

As you can see, this template is definitely NOT for newcomers. 
Users of this template are expected to have experiences on modding two or more Minecraft versions ~~, as well as 
experiences with different modding frameworks (Fabric, Forge, Quilt, ...)~~

If you want something much simpler, [jaredlll08/MultiLoader-Template][ref-jared-template] is also a good start. 
That template focuses on one specific Minecraft version, which is much more conventional.

[ref-jared-template]: https://github.com/jaredlll08/MultiLoader-Template

The name of this template `Pāramitā` is [IAST][ref-IAST] of Sanskrit पारमिता, usually translated as "perfection", or 
less commonly interpreted as "that which goes beyond". 

[ref-IAST]: https://en.wikipedia.org/wiki/International_Alphabet_of_Sanskrit_Transliteration

## Usage

1. Simply clone the repository and start adding/removing subprojects based on your need.

2. Purge the entire `.git` directory and then `git init` if you need a fresh start of your `git` history.

3. Change the mod name from `ExampleMod` to something else, also replace other template things like `modId="test_multi_project_mod_please_ignore"`.

4. As a compromise between directly copying files and using C-like Manifold macros, we encourage the use of symbolic links (soft links) to reduce duplicate code:
    1. Run the following command in your terminal:
    ```
    git config --global core.symlinks true
    ```
    2. For Windows users:
       1. Enable Developer Mode in system settings. 
       2. In the project root directory, you will find a script named `softlink_create.bat`. To create a soft link, simply drag and drop the original file onto this .bat file (a.k.a. open it with the .bat file).
    3. For Linux/macOS users, Creating symbolic links from the command line should be straightforward.

Remember,

 - Version-specific code goes to version-specific projects.

All `build.gradle` files should give you enough hint about what do they do.

### How to know which projects do I need?

Depends on your actual need. You probably want the latest version (as of today, it is 1.19.3) first. 
Nevertheless, here are a few things to consider: 

  - Maintaining too many loader+version combinations can make you burn out *very fast*. You have been warned.
  - If you are on/want 1.19.*, you will need all of `1.19.2`, `1.19.3` and `1.19.4` subprojects if:
    - You have new items (due to creative tabs changes between `1.19.2` and `1.19.3`)
    - You have anything to do with `BakedModel` (due to various changes between `1.19.2` and `1.19.3`)
    - You have direct reference to `ItemTransforms.TransformType` (`ItemDisplayContext` succeeds it in `1.19.4`)
    - *to be continued*
  - If you are on/want 1.18.*, you will need both `1.18.1` and `1.18.2` subprojects if:
    - You have anything to do with world generation
  - *To be continued*

## Credits

Special thanks to 3TUSK, he made the previous version of Paramita.

Special thanks to williewillus, Hurby, Alwinfy, et al. for their multi-loader project architecture used in Botania;
without their pioneering work, this gigantic project layout will not be possible. 

Special thanks to Architectury team for their work on Architectury Loom, which enables the usage of full 
Official Mapping on Forge with Minecraft 1.14 - 1.16.5. 

Special thanks to all developers behind these projects:

  - Architectury Loom
  - Fabric Loom
  - ForgeGradle
  - Librarian (by ParchmentMC)
  - MixinGradle
  - Quilt Loom
  - VanillaGradle

## Further Reading

- [Williewillus, Hubry, Alwinfy. "Maintaining Botania for Forge and Fabric — Multiloader Experience Report", BlanketCon 22.][ref-1]
- [Darkhax, Jared. "MultiLoader Madness", BlanketCon 22.][ref-2]

[ref-1]: https://www.youtube.com/watch?v=EZ-Lvtx6Wyk&list=PLC1qq1Hb0u1GI8919iCClzb_Bku-DrL4L&index=11
[ref-2]: https://www.youtube.com/watch?v=Ec8AoD29lrw&list=PLC1qq1Hb0u1GI8919iCClzb_Bku-DrL4L&index=17
