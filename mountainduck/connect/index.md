Connect mode
===

```{toctree}
:hidden:
:titlesonly:
integrated
sync
online
```

When connecting to a server, you can choose between *[Online](online.md)* and *[Smart Synchronization](sync.md)* connect
mode.

```{admonition} Integrated
The _Integrated_ connect mode synchronizes files and folders from a directory on the local disk with support from macOS and Windows.
```

```{admonition} Online
In _Online_ connect mode, changes to a file are immediately uploaded and in sync when an application has finished saving a file.
```

```{admonition} Smart Synchronization
In _Smart Synchronization_ connect mode, files are copied to a local cache for faster access prior synchronization with the server in the background.
```

## Feature Comparison

|                                          | **Online**                                                            | **Smart Synchronization**                                                     | **Integrated**                                              |
|------------------------------------------|-----------------------------------------------------------------------|-------------------------------------------------------------------------------|-------------------------------------------------------------|
| **Offline Access**                       | –                                                                     | ✔ Save files in cache on disk for access with no server connectivity          | ✔                                                           |
| **Index Files**                          | –                                                                     | Index folder contents in cache on disk for access with no server connectivity | –                                                           |
| **Buffer file contents**                 | ︎Temporarily save opened files for faster access later                | Temporarily save opened files to copy to cache on disk                        | –                                                           |
| **Synchronization**                      | Changes are immediately uploaded                                      | Synchronize changes in the background                                         | ✔                                                           |
| **Transfer Progress**                    | Upload shown in progress window in _Finder.app_ or _Windows Explorer_ | Uploads shown in the status bar (macOS) or taskbar (Windows)                  | Uploads shown in progress icon in Finder & Windows Explorer |
| **[Recent Files](sync.md#recent-files)** | –                                                                     | Available in the status bar (macOS) or taskbar (Windows)                      | ✔                                                           |
| **[Lock Files](../locking.md)**          | ✔︎                                                                    | ✔                                                                             | –                                                           |
| **[Share Files](../share.md)**           | ✔                                                                     | ✔                                                                             | ✔                                                           |
