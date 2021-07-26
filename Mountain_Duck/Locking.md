File Locking
===

Mountain Duck supports locking files to prevent conflicting edits from other while a document is open in an editor.

# Native server-side locking

File locking is natively supported for the following protocols:

- [Dropbox for Business](../Protocols/Dropbox)
- [Microsoft OneDrive](../Protocols/OneDrive)
- [Microsoft SharePoint](../Protocols/SharePoint)
- [WebDAV](../Protocols/WebDAV/index)

```{note}
Some WebDAV implementations including [ownCloud]() and [NextCloud]() may not support locing documents. Make sure to select *Nextcloud & ownCloud* in the bookmark configuration to make use of pseudo locking.
```

Files opend from one of the supported protocols are locked for editing by other users. Mountain Duck locks files on the server when opened in an editor. This prevents other users from modifying the document until the file is closed by the user.

# Pseudo locking for protocols with no native lock support using lock owner files

For connectionc other than [WebDAV](../Protocols/WebDAV/index), we support detecting files opened by others by looking for owner lock files uploading to the server.

```{note}
Support is currently limited to files edited in *Microsoft Word, Microsoft Excel, and Microsoft Powerpoint* on macOS and Windows.
```

## References

When a previously saved file is opend for editing, for printing, or for review, Word creates a temporary file that has a .doc file name extension. This filename extension begins with a tilde (~) that is followed by a dollar sign ($) that is followed by the remainder of the original file name. This temporary file holds the login name of the person who opens the file. This temporary file is called the "owner file".

- [Description of how Word creates temporary files](https://support.microsoft.com/en-us/help/211632/description-of-how-word-creates-temporary-files)
- [The document is locked for editing by another user error message when you try to open a document in Word](https://support.microsoft.com/en-us/help/313472/the-document-is-locked-for-editing-by-another-user-error-message-when)

# Error message when opening locked documents

Attempting to open a locked document, an error message is displayed notifying the document can only be opened in read-only mode. Samples of error messages from different applications.

`````{tabs}
````{group-tab} macOS
**Microsoft Word**<br/>
`Read Only. To save a copy of this document, click Duplicate`

```{image} _images/Read_Only_Microsoft_Word_macOS.png
:alt: Send Command
:width: 500px
```

**Libre Office**<br/>
`Document ... is locked for editing by... . Open document read-only or open a copy of the document for editing.`

```{image} _images/Document_in_Use_Libre_Office_macOS.png
:alt: Send Command
:width: 400px
```

```{image} _images/Read_Only_Mode_Libre_Office_macOS.png
:alt: Send Comman
:width: 400px
```

````
````{group-tab} Windows
`This file is already opend by another user. Would you like to make a copy of this file for your use?`

```{image} _images/File_in_Use_Microsoft_Word_Windows.png
:alt: Send Command
:width: 400px
```

Choose *Receive notification when the original copy is available* to open the document in read-only mode and get an alert when the other user has closed the document.

```{image} _images/Microsoft_Word_Read-Only_Edit_Windows.png
:alt: Send Command
:width: 400px
```

```{image} _images/Microsoft_Word_File_Now_Available_Windows.png
:alt: Send Command
:width: 400px
```

**Microsoft Excel**<br/>
`File in Use: File is locked for editing by ... . Open 'Read-Only' or click 'Notify' to open read-only and receive notification when the document is no longer in use.`

```{image} _images/Read_Only_Microsoft_Excel_Windows.png
:alt: Send Command
:width: 400px
```

Choose *Notify* to open the document in read-only mode and get an alert when the other user has closed the document.

```{image} _images/Microsoft_Excel_File_Now_Available_Notification_Windows.png
:alt: Send Command
:width: 400px
```

````
`````

# Resolution

If you get a warning that the document is *Read-Only*, ask other users to close the document. If the *Read-Only* warning prevails, these are the steps to follow.

- If you are connecting to a WebDAV server with lock support, ask the server administrator to clean up locks on the server.
- For all other servers, delete the file named `~$...`.

# Preferences

Locking is disabled by default. Refer to [Preferences](Preferences) to enable it in *Connection → Locking → Lock Files*.