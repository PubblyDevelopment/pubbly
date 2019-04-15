# Pubbly

Pubbly is a collection of software projects used to create Team CCI's winning submission to the Global Learning Xprize.

## Overview

Pubbly is comprised is four major (and one minor) software projects, each in it's own repository, each with a specific README.

* [Pubbly Design Tools](https://github.com/PubblyDevelopment/pubbly_design_tools)

A cross platform desktop application used to design interactive eBooks.

* [Pubbly Engine](https://github.com/PubblyDevelopment/pubbly_engine)

A javascript engine which takes the XML and assets generated by the design tools and turns them into HTML5 interactive experiences

* [Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console)

A LAMP CMS used to template and manage "exports" created from the design tools.

* [Pubbly SchoolHouse](https://github.com/PubblyDevelopment/pubbly_schoolhouse)

A simple Cordova project where you can plug in content made with the Pubbly Design Tools and Console, attach the HTML5 Pubbly Engine, and build an android APK.

* [Pubbly Submission Installation](https://github.com/PubblyDevelopment/pubbly_submission_installation)

Bash and Shell scripts to take the android image files generated from SchoolHouse steps and mass-install on hundreds of tablets.

---

CCI developed the many pubbly tools and features partly to accommodate the Xprize program, but also to meet other internal needs. We believe our tools can help to edit or translate the existing Xprize English and Swahili programs. We also believe they are sophisticated enough to create completely unrelated educational programs.

The goal of the pubbly system is to take raw assets (images, audio files, video files), create interactive HTML5 books, package them as a "programs" to be deployed as offline/hosted HTML files, or as Cordova wrapped native mobile applications.

## Submission from scratch

It is entirely possible to create a brand new program from brand new assets using our tools. This is a large job, and will take artists, content creators, and developers. For instructions on how to modify our existing program, a much easier task, skip to section "Submission from existing content".

### Submission from scratch: Content creation

The first thing you'll need to do is install the [Pubbly Design Tools](https://github.com/PubblyDevelopment/pubbly_design_tools) on a few work machines, detailed instructions available at [Pubbly Design Tools](https://github.com/PubblyDevelopment/pubbly_design_tools) section "Getting Started".

Once installed, you can create export zips. These zip files are designed to upload to a Pubbly Console CMS, but you can also attach the Pubbly Engine manually to make them into HTML web pages directly. For instructions on how to author books, use the design tools' built in help menus, or watch our [Youtube tutorials](https://www.youtube.com/channel/UCnkoKt9PYqaMumT1V2giGbQ). For instructions on creating export zips, see [Pubbly Design Tools](https://github.com/PubblyDevelopment/pubbly_design_tools) section "Exports". For Instructions on creating your own Pubbly Console and uploading export zips, see [Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) section "Adding content". For Instructions on how to manually attach the HTML5 engine for offline, server side, or cordova app integration, see [Pubbly Engine](https://github.com/PubblyDevelopment/pubbly_engine) section "Attaching".

### Submission from scratch: Content management

There are a variety of different methods to organize, template, assemble and structure Design Tools Exports. Content can be

* Upload in an as is state
[Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) section "Adding content: Uploading to Static"
* Template for mass production
[Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) section "Adding content: Uploading to Variable"

Once content has been uploaded to the console, it can be reassembled by 

* Stitch pages from Static/Variable sources into a single congregate
[Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) section "Assembling content: Stitching"
* Mapping out multiple books and link them together
[Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) section "Assembling content: Mapping"

All content on a console can be downloaded and re-edited in the Design Tools. For help doing that, see [Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) section "Downloading/Editing content".

### Submission from scratch: Content deployment

Once all content for your program has been finished, you can create and deploy "packets". A "packet" is an export, ready to be hosted on a website or wrapped into an APK. You can create packets from Static/Variable exports, from an entire school hierarchy of Stitched Exports, and from an entire Map. For instructions, see [Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) section "Creating packets"

Each packet is an HTML file, an XML file, and folders full of assets (images, audio, and video files). The HTML file loads the Pubbly Engine, a collection of javascript required to "run" the experience. The Javascript loads the XML file, which gives it instructions as to which assets should be displayed where, and in what ways the end reader can interact in the overall experience.

Maps can be built as stand alone APKs quite easily, as they are usually smaller in size and (if unzipped at cordova web root) require no front end UI. For instructions on how to make a Map into a standalone export, see [Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) section "Creating packets: Mapped Exports". However, Pubbly's Xprize program used a combination of all available export types, loosely bound by a light and somewhat messy custom front end. To repurpose our front end, see [Pubbly SchoolHouse](https://github.com/PubblyDevelopment/pubbly_schoolhouse) section "Repurposing with new content")

## Submission from existing content

If you do not have the time or resources to create your own program, you are more than welcome to use our existing Xprize submission as a base. 

### Submission from existing: Direct asset modification

The easiest way to slightly modify our submission is to directly edit the assets in their respective cordova roots. For instructions on how to use either language's root folder to duplicate our exact Xprize submission, see [Pubbly SchoolHouse](https://github.com/PubblyDevelopment/pubbly_schoolhouse) section "Adding content: Xprize web roots".

Once you have the language specific root folder inside a properly structured cordova project, manually edit targeted assets and rebuild the cordova project.

### Submission from existing: Xprize console duplication

The second easiest way to modify our existing submission is to duplicate not only our console code base, but all xprize related content as well. First, create a new empty [Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) (section "Getting started"). Log into your console, download and unzip the Xprize console content zips to their local folders, and import an associated sql file.

| Type             |                      Zip location                      |   Extract location    |
|------------------|:------------------------------------------------------:|:---------------------:|
| Static Exports   |  xprize.pubbly.com/DuplicateConsole/StaticExports.zip  |  /var/www/html/books  |
| Variable Exports | xprize.pubbly.com/DuplicateConsole/VariableExports.zip | /var/www/html/series  |
| Stitched Exports | xprize.pubbly.com/DuplicateConsole/StitchedExports.zip | /var/www/html/schools |
| Mapped Exports   |  xprize.pubbly.com/DuplicateConsole/MappedExports.zip  |   /var/www/html/map   |
| Content SQL file |     xprize.pubbly.com/DuplicateConsole/Content.sql     |       mysql db        |

* Log into your personal console using SSH (EG putty)
> Add the base sql structure if you haven't already (i.e. finish [Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) section "Getting started")
> Download content zips from our Xprize server to a local folder
* cd ~/
* mkdir tmp
* cd tmp
* wget xprize.pubbly.com/DuplicateConsole/StaticExports.zip
* wget xprize.pubbly.com/DuplicateConsole/VariableExports.zip
* wget xprize.pubbly.com/DuplicateConsole/StitchedExports.zip
* wget xprize.pubbly.com/DuplicateConsole/MappedExports.zip
> Unzip content to respective web roots
* sudo apt-get install unzip
* sudo unzip StaticExports.zip -d /var/www/html/books
* sudo unzip VariableExports.zip -d /var/www/html/series
* sudo unzip StitchedExports.zip -d /var/www/html/schools
* sudo unzip MappedExports.zip -d /var/www/html/map
> (re)Fix permissions issues
* cd /var/www/html
* sudo chmod 755 books series schools map zips deleted* -R
* sudo chown www-data:ubuntu books series schools map zips deleted* -R
> Download and import a sql file which reflects your new content.
* wget xprize.pubbly.com/DuplicateConsole/Content.sql
* sudo mysql -u root -p pubbly_console < Content_Ordered.sql
> Cleanup
* cd ../
* rm -r tmp

You now have an exact snapshot (minus user accounts) of the console TeamCCI used to create the Xprize English/Swahili program.

For how this content can be supplemented, edited, modified, or removed from the console, see [Pubbly Console](https://github.com/PubblyDevelopment/pubbly_console) section "Adding content" 

### Submission from existing: Design overview.

In Stitch App you will see an English XPRIZE School and the Swahili XPRIZE School. You will need to create a new “School”. For example “French School”. Here you will gather all your books and lessons that will be in the program according to level. In each level build the games that are appropriate for that level. Games will have three levels of difficulty. Create new children in each game series and swap in the visual assets and audio assets to customize for the new language.

Model your build on either the English or Swahili Build. To see which series an element in Stitch App comes from -- hover over the page and the title of the series will show.

Content is updated and created in the Variable Exports and Static Exports sections of the console. Swaps are done in the console in Variable Assets. Create new children in existing series to swap. New lessons are created in the PUBBLY desktop application and uploaded into new series in Variable Assets or Static Assets. See [YouTube tutorials](https://www.youtube.com/channel/UCnkoKt9PYqaMumT1V2giGbQ) on how to build from scratch.

#### Submission from existing: Math content

For lessons, download all art that is in English or Swahili. Retain same size of art in GIMP/similar and update with the new language. Create a new child in the series and drop new assets into the lesson. Click “view” to view updated lesson.
-- You can also download the lessons and make changes. Create a new series and upload the new lesson. Swaps for languages can be done in the new series.
-- You can stitch the lesson pages you want in Units. Some of the lessons contain reviews that can be taken out
-- If you download a parent and make changes to that parent in the PUBBLY desktop application and then upload that parent into an existing series -- all the children will be updated.

#### Submission from existing: Reading and Writing content

All Languages are taught differently. Lessons in another language can reuse assets or add new art. We would suggest you based your lessons on an early language learners program and build your lessons from scratch. You can watch our YouTube videos for help to build new lessons.
https://www.youtube.com/channel/UCnkoKt9PYqaMumT1V2giGbQ

#### Submission from existing: Bookshelf content

Download pages and replace text with new language keeping the same size PNG or JPEG. Create a child in the series with the new languages name. Swap in new art and swap in new audio. Click view on new child to see the updated book.

#### Submission from existing: Epic quest content

We recommend downloading each element of the quest you want to use and updating it with your new language and then creating a new folder in Series call EpicQuestFrench. Use “Maps” to connect all the TBD nodes.

#### Submission from existing: Notes.

Keep all pages the same size so that they can be stitched to other pages. 1000 x 641 is what most of our screen sizes are. This was done for the Pixel C. These programs will also run on desktop online or locally.

## Xprize code base

All related Xprize code is open and Apache 2.0 licensed in the 4 linked to repositories. Each repository has a "FOR DEVELOPERS" sections, and the code is (hopefully) adequately commented. All repositories will be actively maintained for as long as possible, hopefully forever.

## Credits

Josh Powe: CEO

Susan Darwin: PUBBLY Creative Director

Richard Lopez: PUBBLY Designer/Associate Animation Director

David Wanta: PUBBLY Designer/Animator

Errol Hicks: PUBBLY Designer/Animator

### Software: 

Jason Horsley: CTO

Ray Horsley: Application developer

Wallis Muraca: Junior Developer

### Content:

Curriculum Concepts International (CCI)

PUBBLY Creative Team