# Disk space

```bash
df -h                 # free space
du -h --max-depth=1   # disck usage at current level
du -h --max-depth=1 2> /dev/null    # remove stderr Permission denied
```

# Ssh Keys

```bash
ssh-keygen -t rsa -b 4096 -f .ssh/id_rsa_XYZ
```


# install executables

```bash
mv ./<exec> /usr/local/bin/
chmod 755 /usr/local/bin/<exec>
```

# System Info

```bash
less /proc/cpuinfo      # CPU INFO
free -m (-m MB, -g GB)  # RAM INFO
```

# Find Files

```bash
find / -name <FILE_NAME_EXPR> 2>&1 | grep -v "Permission denied"
```

# Grep 
```bash
grep -rnw /<path>/ -e '<expr>' # find text in files
```

# Zip/Unzip Files

```bash
zip [-options] [-b path] [-t mmddyyyy] [-n suffixes] [zipfile list] [-xi list]
  The default action is to add or replace zipfile entries from list, which
  can include the special name - to compress standard input.
  If zipfile and list are omitted, zip compresses stdin to stdout.
  -f   freshen: only changed files  -u   update: only changed or new files
  -d   delete entries in zipfile    -m   move into zipfile (delete OS files)
  -r   recurse into directories     -j   junk (don't record) directory names
  -0   store only                   -l   convert LF to CR LF (-ll CR LF to LF)
  -1   compress faster              -9   compress better
  -q   quiet operation              -v   verbose operation/print version info
  -c   add one-line comments        -z   add zipfile comment
  -@   read names from stdin        -o   make zipfile as old as latest entry
  -x   exclude the following names  -i   include only the following names
  -F   fix zipfile (-FF try harder) -D   do not add directory entries
  -A   adjust self-extracting exe   -J   junk zipfile prefix (unzipsfx)
  -T   test zipfile integrity       -X   eXclude eXtra file attributes
  -y   store symbolic links as the link instead of the referenced file
  -e   encrypt                      -n   don't compress these suffixes
  -h2  show more help
  
zip <zip_file_name> -r <folder_to_zip> <folder_to_zip> <folder_to_zip> ...  # Zip Folders
zip <zip_file_name> <file_to_zip> <file_to_zip> <file_to_zip> ...           # Zip Files

Usage: unzip [-Z] [-opts[modifiers]] file[.zip] [list] [-x xlist] [-d exdir]
  Default action is to extract files in list, except those in xlist, to exdir;
  file[.zip] may be a wildcard.  -Z => ZipInfo mode ("unzip -Z" for usage).

  -p  extract files to pipe, no messages     -l  list files (short format)
  -f  freshen existing files, create none    -t  test compressed archive data
  -u  update files, create if necessary      -z  display archive comment only
  -v  list verbosely/show version info       -T  timestamp archive to latest
  -x  exclude files that follow (in xlist)   -d  extract files into exdir
modifiers:
  -n  never overwrite existing files         -q  quiet mode (-qq => quieter)
  -o  overwrite files WITHOUT prompting      -a  auto-convert any text files
  -j  junk paths (do not make directories)   -aa treat ALL files as text
  -U  use escapes for all non-ASCII Unicode  -UU ignore any Unicode fields
  -C  match filenames case-insensitively     -L  make (some) names lowercase
  -X  restore UID/GID info                   -V  retain VMS version numbers
  -K  keep setuid/setgid/tacky permissions   -M  pipe through "more" pager

unzip <zip_file_name>
```

# Curl

```bash
curl --noproxy "*" -v -k -u <USERNAME:PASSWORD> --upload-file <file_to_upload> <URL> or <URL>/<file_to_upload_new_name>   #Upload File
```
