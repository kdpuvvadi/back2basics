---
title: Linux basic commans
date: 2022-08-22 10:14:15 +0530
categories: [Basics, Linux]
tags: [basics, linux, bash]
---

## Create a directory

create a directory with `mkdir`

```bash
mkdir dir1
```

## Change directory

change to a directory with `cd`

```bash
cd dir1
```

## Current Directory

Check your current working directory with `pwd`

```bash
pwd
/home/back2basics/dir1
```

To change current directory from `/home/back2basics/dir1` to `/home/back2basics/`

```bash
cd ../
```
To change directory from `/home/back2basics/dir1` to `/home/`

```bash
cd ../../
```

check current directory with `pwd`

```bash
pwd
/home
```

## List of files

To list files and directories in a perticuler directory use `ls`

```bash
ls
dir1  dir2  dir3  dir4  file1  file2  file3
```

To list the in long format `ls -l`

```bash
ls -l
total 16
drwxr-xr-x 2 back2basics back2basics 4096 Aug 22 12:11 dir1
drwxr-xr-x 2 back2basics back2basics 4096 Aug 22 12:11 dir2
drwxr-xr-x 2 back2basics back2basics 4096 Aug 22 12:11 dir3
drwxr-xr-x 2 back2basics back2basics 4096 Aug 22 12:11 dir4
-rw-r--r-- 1 back2basics back2basics    0 Aug 22 12:12 file1
-rw-r--r-- 1 back2basics back2basics    0 Aug 22 12:12 file2
-rw-r--r-- 1 back2basics back2basics    0 Aug 22 12:12 file3
```

To view hidden  `ls -a`

```bash
ls -a
.  ..  .file4  dir1  dir2  dir3  dir4  file1  file2  file3
```

here `file4` is hidden

to view files in long format with hidden visibil `ls -la`

```bash
ls -la
total 24
drwxr-xr-x  6 back2basics back2basics 4096 Aug 22 12:12 .
drwxr-xr-x 17 back2basics back2basics 4096 Aug 22 12:11 ..
-rw-r--r--  1 back2basics back2basics    0 Aug 22 12:12 .file4
drwxr-xr-x  2 back2basics back2basics 4096 Aug 22 12:11 dir1
drwxr-xr-x  2 back2basics back2basics 4096 Aug 22 12:11 dir2
drwxr-xr-x  2 back2basics back2basics 4096 Aug 22 12:11 dir3
drwxr-xr-x  2 back2basics back2basics 4096 Aug 22 12:11 dir4
-rw-r--r--  1 back2basics back2basics    0 Aug 22 12:12 file1
-rw-r--r--  1 back2basics back2basics    0 Aug 22 12:12 file2
-rw-r--r--  1 back2basics back2basics    0 Aug 22 12:12 file3
```

sort items by time with `-t`

```bash
ls -t
file3  file2  file1  dir4  dir3  dir2  dir1
```

with long list `-lt`

```bash
ls -lt
total 16
-rw-r--r-- 1 kd kd    0 Aug 22 12:24 file3
-rw-r--r-- 1 kd kd    0 Aug 22 12:12 file2
-rw-r--r-- 1 kd kd    0 Aug 22 12:12 file1
drwxr-xr-x 2 kd kd 4096 Aug 22 12:11 dir4
drwxr-xr-x 2 kd kd 4096 Aug 22 12:11 dir3
drwxr-xr-x 2 kd kd 4096 Aug 22 12:11 dir2
drwxr-xr-x 2 kd kd 4096 Aug 22 12:11 dir1
```

with hidden files `-lta`

```bash
ls -lta
total 24
drwxr-xr-x  6 kd kd 4096 Aug 22 12:27 .
-rw-r--r--  1 kd kd    0 Aug 22 12:24 file3
-rw-r--r--  1 kd kd    0 Aug 22 12:12 .file4
-rw-r--r--  1 kd kd    0 Aug 22 12:12 file2
-rw-r--r--  1 kd kd    0 Aug 22 12:12 file1
drwxr-xr-x  2 kd kd 4096 Aug 22 12:11 dir4
drwxr-xr-x  2 kd kd 4096 Aug 22 12:11 dir3
drwxr-xr-x  2 kd kd 4096 Aug 22 12:11 dir2
drwxr-xr-x  2 kd kd 4096 Aug 22 12:11 dir1
drwxr-xr-x 17 kd kd 4096 Aug 22 12:11 ..
```

## Create files (touch)

To create a file with `touch`

```bash
touch file1
```
touch creates empty files or updates timestamps of the perticuler file.

## Copying files

To copy file to another with `cp`

```bash
cp file1 to file2
```

To copy file from one directory to another

```bash
cp dir1/file1 dir2/file1
```

To copy one directory to another, use `-r` to copy all files inside recursively 

```bash
cp -r dir1 dire2
```

## Moving Files

To move file with `mv`

```bash
mv file1 to file2
```

To move file from one directory to another

```bash
mv dir1/file1 dir2/file1
```

To move one directory to another, use `-r` to copy all files inside recursively 

```bash
mv -r dir1 dire2
```
