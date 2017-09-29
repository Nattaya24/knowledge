#List the Files in a Directory/Folder

##Description

These functions produce a character vector of the names of files or directories in the named directory.

Usage

list.files(path = ".", pattern = NULL, all.files = FALSE,
           full.names = FALSE, recursive = FALSE,
           ignore.case = FALSE, include.dirs = FALSE, no.. = FALSE)

       dir(path = ".", pattern = NULL, all.files = FALSE,
           full.names = FALSE, recursive = FALSE,
           ignore.case = FALSE, include.dirs = FALSE, no.. = FALSE)

list.dirs(path = ".", full.names = TRUE, recursive = TRUE)
Arguments

path	
a character vector of full path names; the default corresponds to the working directory, getwd(). Tilde expansion (see path.expand) is performed. Missing values will be ignored.
pattern	
an optional regular expression. Only file names which match the regular expression will be returned.
all.files	
a logical value. If FALSE, only the names of visible files are returned. If TRUE, all file names will be returned.
full.names	
a logical value. If TRUE, the directory path is prepended to the file names to give a relative file path. If FALSE, the file names (rather than paths) are returned.
recursive	
logical. Should the listing recurse into directories?
ignore.case	
logical. Should pattern-matching be case-insensitive?
include.dirs	
logical. Should subdirectory names be included in recursive listings? (They always are in non-recursive ones).
no..	
logical. Should both "." and ".." be excluded also from non-recursive listings?
Value

A character vector containing the names of the files in the specified directories, or "" if there were no files. If a path does not exist or is not a directory or is unreadable it is skipped, with a warning.

The files are sorted in alphabetical order, on the full path if full.names = TRUE.

list.dirs implicitly has all.files = TRUE, and if recursive = TRUE, the answer includes path itself (provided it is a readable directory).

Note

File naming conventions are platform dependent. The pattern matching works with the case of file names as returned by the OS.

path must specify paths which can be represented in the current codepage, and files/directories below path whose names cannot be represented in that codepage will most likely not be found.

Author(s)

Ross Ihaka, Brian Ripley

See Also

file.info, file.access and files for many more file handling functions and file.choose and choose.files for interactive selection.

glob2rx to convert wildcards (as used by system file commands and shells) to regular expressions.

Sys.glob for wildcard expansion on file paths.
