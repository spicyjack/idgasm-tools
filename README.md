## WAD Tools ##

A bunch of tools that interact with WAD files from the games 
Doom/Doom II/Heretic/Hexen/Strife and others.

There's also tools that will interact with the `Doomworld idGames Archive`
(http://www.doomworld.com/idgames), a web front end with extra functionality
(ratings, searching, and more) on top of the `idGames Archive` FTP/HTTP
service via the [idGames Archive API](http://www.doomworld.com/idgames/api).

### What's in this repo? ###

#### `App::WADTools` ####
The Perl distribution `App::WADTools` is a set of tools that will index/catalog
`WAD` files stored on the local machine, as well as query the [idGames Archive
API](http://www.doomworld.com/idgames/api) and download different
records from the serivce into a local database file.

The local database files are [SQLite](http://www.sqlite.org/) files that are
generated from [INI](https://metacpan.org/pod/Config::Std) files using a
specific format.

### Scripts included with this distribution ###

**idgames_db_dump**
- Queries the [idGames Archive API](http://www.doomworld.com/idgames/api)
  starting at file ID #1, and up to the latest entry in the `idGames Archive`

**db_tool**
- Create/update [SQLite](http://www.sqlite.org/) database files, which can be
  used with `idgames_db_dump`

**wadindex**
- Creates an index and/or a catalog of files using a local copy of the
  `idGames Archive`.
  - An _index_ is a mapping of WAD levels to files in the local copy of
    `idGames Archive`
  - A _catalog_ is a complete listing of resources used in a `WAD` file,
    including vertexes, sectors, textures, sprites and audio.

**dump_o_matic**
- Combines the contents of one or more databases into a new database file

#### `scripts` Directory ####

##### sum_all_text_files.sh #####
Runs through a local copy of the `idGames Archive`, and sums all of the text
files located in directories known to contain WAD files.  This is used to give
a rough estimate of how much data would be bundled with applications that
would want to keep a cached copy of the `idGames Archive` info to use while
the application is running

vim: filetype=markdown shiftwidth=2 tabstop=2
