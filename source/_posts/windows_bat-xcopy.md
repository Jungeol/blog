---
title: windows_bat-xcopy
tag: windows_bat
category: windows_bat
date: 2019-12-04 21:40:29
---
## xcopy
.bat file
```
SET START_DATE=11-23-2017
SET BAT_PATH=%~dp0
SET EXPORT_FOLDER=%~dp0..\_files_export_by_date

xcopy %BAT_PATH%*.* %EXPORT_FOLDER% /Y /S /EXCLUDE:%BAT_PATH%xcopy_exclude_by_date /D:%START_DATE%
```
exclude file
```
ParsingPdf.pdb
ParsingPdf.vshost.exe
.suo
.e2e
.log
hidden_changes.conf
\dll\
\bin\
\obj\
\temp\html\
\extjs\ext
\generator\
\ActionProviderImplementation\
\plugin\cmis_app\
.csproj
.csproj.user
.config
.dbml
.dbml.layout
.designer.cs
.Designer.cs
.settings
\scripts\
```