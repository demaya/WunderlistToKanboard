WunderlistToKanboard
====================

Quick and dirty PHP script to import Wunderlist (http://www.wunderlist.com/) tasks and lists in a kanboard (http://kanboard.net/) database

## Prerequisites

  - PHP (any 5.x version should work, this script was tested on PHP 5.3.27) with SQLite 3 support
  - A command line interpreter
  - Kanboard 1.0.3 **/!\ this script was tested on this version only**
  - Wunderlist web application (tested on 2.3.6.1)
  - A beer

## Quick usage

  1. Get the script here : https://github.com/EpocDotFr/WunderlistToKanboard/archive/master.zip and unzip the content somewhere on your computer
  2. Go to the Wunderlist settings > **Account** tab, click on the **Create backup** button, and download the backup file
  3. Rename the downloaded file to `wunderlist.json`
  4. Download your original Kanboard database (via FTP or via the **Settings** tab > **Download the database** link. Remember : Kanboard 1.0.3  only). Don't forget to make a backup
  5. Throw these two files in the script directory. Your should have at this time `wunderlist.json` and `db.sqlite` next to the `run.php` file
  6. In your command line interpreter, launch `php run.php`. You should see some logging message
  7. If all is good, replace the old Kanboard database with the new one (e.g via FTP)
  8. Your lists and tasks has now been imported. You can drink your beer :)

## Options

You can define some settings like changing the generated colum names to match your language. See in the `run.php` file.

## How it works

The `run.php` file is quite commented (I think) if you want to know more.

Kanboard and Wunderlist are very different, so there's some things to know about what happens to your tasks and lists in certain cases :

  - Lists are imported as Projects
  - The default Kanboard's columns are created for each imported projects ()
  - Users cannot be imported
  - Comments cannot be imported
  - Starred tasks will have a color of red, otherwise yellow (Kanboard's default)
  - Sub-tasks are merged in their main task's description

All the other data supported by Kanboard is imported with no problems.

## End words

If you have questions or problems, you can [submit an issue](https://github.com/EpocDotFr/WunderlistToKanboard/issues).
