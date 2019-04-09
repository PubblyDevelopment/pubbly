> How to deactivate/activate kiosk mode. It is up to each individual team to determine if
you want that available from day one, or if the deactivation occurs once a certain amount
of curriculum is completed.

To deactivate/activate Kiosk mode, consult the [Pubbly SchoolHouse](https://github.com/PubblyDevelopment/pubbly_schoolhouse) repository's build instructions, specifically section "Installing APK: (Optional) DO NOT Force a locked Kiosk mode"

> How to compile the source code for an Android device that is not the Google Pixel C.

The program was originally built as an APK. The supplied build instructions will work for any targeted android 7 device, and may work for other android OS versions, or on iOS, but both are untested.

[Pubbly SchoolHouse](https://github.com/PubblyDevelopment/pubbly_schoolhouse) section "Building"

> How to install the English version of the software onto an Android device.

Each language was built as a separate APK. For instructions on how to build each, see [Pubbly SchoolHouse](https://github.com/PubblyDevelopment/pubbly_schoolhouse) section "Adding content: Xprize web roots"

> How to switch between Swahili and English language when using the software.

Languages cannot be switched during use. Each language was built as a separate APK. For instructions on how to build each, see [Pubbly SchoolHouse](https://github.com/PubblyDevelopment/pubbly_schoolhouse) section "Adding content: Xprize web roots"

> How to add support for a new language. A list of necessary code/asset modifications.

There are three methods for repurposing our submission for another language.

1. (quick) Directly modify image and audio files inside the Xprize web root folders
2. (medium) Create a new Pubbly Console (CMS) with all Xprize related assets preloaded, and use that as a jumping off point for a new program
3. (long) Create a new program from scratch using our tools

> Please include step-by-step instructions on how to perform the above listed items. As
detailed as possible, using actual commands (not freetext). We suggest you create two
files: INSTALL.md (compile and install)

For instructions on the first method, see [Pubbly](https://github.com/PubblyDevelopment/pubbly) section "Submission from existing: Direct asset modification"

However, it is our belief that each language is too unique for a true "one size fits all" approach. So although you could directly translate every audio file and image with text, we do not think it would produce quality educational material. 

For instructions on the second, see [Pubbly](https://github.com/PubblyDevelopment/pubbly) section "Submission from existing: Xprize console duplication"

For instructions on the third, see [Pubbly](https://github.com/PubblyDevelopment/pubbly) section "Submission from scratch"
