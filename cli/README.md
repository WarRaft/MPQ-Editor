((макет
((блок33
https://xgm.guru/files/2377/346120/logo1.png
))
((блок66
((макет
((блок66
- Нажмите `Win+R`
- Наберите `cmd`
- Нажмите `Enter`
- Перетащите `MPQEditor.exe` в окно консоли
- Наберите `/console`
- Нажмите `Enter`
))
((блок33
https://xgm.guru/files/2377/346120/cli.mp4
))
))
))
))

# Операции

- [a](https://xgm.guru/p/warraft/MPQ-Editor_CLI#add)
- [add](https://xgm.guru/p/warraft/MPQ-Editor_CLI#add)
- [chdir](https://xgm.guru/p/warraft/MPQ-Editor_CLI#chdir)
- [c](https://xgm.guru/p/warraft/MPQ-Editor_CLI#close)
- [close](https://xgm.guru/p/warraft/MPQ-Editor_CLI#close)
- [compact](https://xgm.guru/p/warraft/MPQ-Editor_CLI#compact)
- [console](https://xgm.guru/p/warraft/MPQ-Editor_CLI#console)
- [d](https://xgm.guru/p/warraft/MPQ-Editor_CLI#delete)
- [delete](https://xgm.guru/p/warraft/MPQ-Editor_CLI#delete)
- [exit](https://xgm.guru/p/warraft/MPQ-Editor_CLI#exit)
- [e](https://xgm.guru/p/warraft/MPQ-Editor_CLI#extract)
- [extract](https://xgm.guru/p/warraft/MPQ-Editor_CLI#extract)
- [f](https://xgm.guru/p/warraft/MPQ-Editor_CLI#flush)
- [flush](https://xgm.guru/p/warraft/MPQ-Editor_CLI#flush)
- [help](https://xgm.guru/p/warraft/MPQ-Editor_CLI#help)
- [htsize](https://xgm.guru/p/warraft/MPQ-Editor_CLI#htsize)
- [l](https://xgm.guru/p/warraft/MPQ-Editor_CLI#list)
- [list](https://xgm.guru/p/warraft/MPQ-Editor_CLI#list)
- [mksvf](https://xgm.guru/p/warraft/MPQ-Editor_CLI#mksvf)
- [m](https://xgm.guru/p/warraft/MPQ-Editor_CLI#move)
- [move](https://xgm.guru/p/warraft/MPQ-Editor_CLI#move)
- [n](https://xgm.guru/p/warraft/MPQ-Editor_CLI#new)
- [new](https://xgm.guru/p/warraft/MPQ-Editor_CLI#new)
- [o](https://xgm.guru/p/warraft/MPQ-Editor_CLI#open)
- [op](https://xgm.guru/p/warraft/MPQ-Editor_CLI#openpatch)
- [open](https://xgm.guru/p/warraft/MPQ-Editor_CLI#open)
- [openpatch](https://xgm.guru/p/warraft/MPQ-Editor_CLI#openpatch)
- [quit](https://xgm.guru/p/warraft/MPQ-Editor_CLI#exit)
- [r](https://xgm.guru/p/warraft/MPQ-Editor_CLI#rename)
- [rename](https://xgm.guru/p/warraft/MPQ-Editor_CLI#rename)
- [script](https://xgm.guru/p/warraft/MPQ-Editor_CLI#script)
- [t](https://xgm.guru/p/warraft/MPQ-Editor_CLI#htsize)
- [v](https://xgm.guru/p/warraft/MPQ-Editor_CLI#version)
- [ver](https://xgm.guru/p/warraft/MPQ-Editor_CLI#version)
- [version](https://xgm.guru/p/warraft/MPQ-Editor_CLI#version)

# add

Добавляет один или несколько файлов в MPQ. Заменяет существующие файлы.

```
a|add MpqFile [SourceFile] [TargetName] [/wav] [/c] [/auto] [/r]
```

MpqFile | Name of the MPQ to be used for this operation.
SourceFile | Name of source file. Can contain wildcards.    
TargetName | Target file name (or directory name) in MPQ.   
/wave | Add the file as WAVE file.                     
/c | Use data file compression.                     
/auto | Choose compression by file type.               
/r | Recurse subdirectories.

## Not enough space on the disk

((макет
((блок50
Ошибка, возникающая при добавлении файлов в архив. Самый простой способ от неё избавиться это нажать кнопку
`Set Max File Count` в интерфейсе редактора.
))
((блок50
https://xgm.guru/files/2377/346120/SetMaxFileCount.png
))
))

# chdir

Changes the current directory.

```
chdir NewDirectory
```

# close

Closes currently open MPQ.
Automatically done at the end of script processing or after `exit` command.

```
c|close
```

# compact

Compacts the MPQ, removing all empty space.

```
compact MpqFile [ListFile]
```

MpqFile | Name of the MPQ to be used for this operation.         
ListFile | Listfile name. If none, the internal listfile is used.
|

# console

Runs the MPQ Editor in the console mode. This command only works from the command line.

```
console
```

Пример:

```
D:\MPQEditor.exe /console
```

# delete

Deletes a file within MPQ.

```
d|delete MpqFile FileName
```

MpqFile | Name of the MPQ to be used for this operation.
FileName | Name of file to be deleted.
|

# exit

Closes the script console.
Also closes opened MPQ.

```
exit|quit
```

# extract

Extracts one or more files from MPQ Archive.

```
e|extract MpqFile FileName [TargetDir] [/listfile FileName] [/fp] [/lower]
```

MpqFile | Name of the MPQ to be used for this operation.
FileName | Full name of file (or wildcard) in the MPQ.
TargetDir | Target dir. If not entered, the current dir will be used.
/listfile | Uses listfile for extraction
/fp | Forces extraction with the path stored in MPQ file
/lower | Creates lowercase path

# flush

Compacts the MPQ, removing all empty space.

```
f|flush MpqFile [ListFile]
```

MpqFile | Name of the MPQ to be used for this operation.
ListFile | Listfile name. If none, the internal listfile is used.
|

# help

Shows basic help about a command.

```
help [command]
```

# htsize

Changes hash table size of the archive.

```
t|htsize MpqFile HashTableSize
```

MpqFile | Name of the MPQ to be used for this operation.               
HashTableSize | File limit. Can be a dec or hex number. Default is `0x1000`.
|

# list

Lists files in MPQ.
Can list them to the screen or to a file.

```
l|list MpqFile [FileMask] [OutFile]
```

MpqFile | Name of the MPQ to be used for this operation.
FileMask | File mask to be listed.
OutFile | Name of text file that contain the file list.

# mksvf

Creates a file that contains MD5 values of each file in the MPQ.

```
mksvf
```

# move

Moves a file within MPQ into another dir.

```
m|move MpqFile FileName NewDirectory
```

MpqFile | Name of the MPQ to be used for this operation.
FileName | Name of file to be moved.
NewDirectory | Target directory within MPQ to move the file to.

# new

Creates a new MPQ. If the file already exists, it will be converted to MPQ.

```
n|new MpqFile [MaxFileCount]
```

MpqFile | Name of the MPQ to be used for this operation.
MaxFileCount | File limit. Can be a dec or hex number. Default is `0x1000`.
|

# open

Opens an existing MPQ. If the file doesn't exist, the function fails.

```
o|open MpqFile [ListFile]
```

MpqFile | Name of the MPQ to be used for this operation.     
ListFile | Name of the listfile to be used on open operation.
|

# openpatch

Opens multiple MPQs in patch mode. If any of the MPQs doesn't exist,
the function fails.

```
op|openpatch BaseMpq PatchName1 PatchName2 ... PatchNameN [/listfile|/lf ListFile1 ... ListFileN]
```

BaseMpq | Name of the base MPQ.                                    
PatchNameX | Name of patch MPQ. Older patch MPQs must come first.     
ListFile | Name(s) of external listfile(s) to be additionally used.

# rename

Renames a file within MPQ.

```
r|rename MpqFile OldFileName NewFileName
```

MpqFile | Name of the MPQ to be used for this operation.
OldFileName | Name of file to be renamed.                   
NewFileName | New name of the file

# script

Processes a MoPaQ 2000 script.

```
script ScriptFile
```

# version

Shows version of MPQ Editor.

```
v|ver|version
```
