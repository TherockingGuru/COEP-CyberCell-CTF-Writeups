# Challenge 06 — Not What It Seems

**Category:** File Forensics

## Objective
Identify the true format of `mystery.jpg` and inspect its contents to find an enclosed `flag.txt`.

## Initial Clue
The challenge gives these first four bytes:

```text
50 4B 03 04
```

This is a common signature for a ZIP local file header.

## Investigation Procedure (Windows PowerShell)
Download `mystery.jpg` from the CTF page and open PowerShell in the directory containing the file.

### 1. Inspect the file signature
```powershell
Format-Hex .\mystery.jpg | Select-Object -First 3
```

The hexadecimal bytes help identify the file's actual format. The challenge's `50 4B 03 04` clue indicates ZIP archive data.

### 2. Make a copy with a ZIP extension
```powershell
Copy-Item .\mystery.jpg .\mystery.zip
```

This changes the copy's filename, not its contents.

### 3. Extract the archive
```powershell
Expand-Archive .\mystery.zip -DestinationPath .\extracted
```

### 4. List extracted files
```powershell
Get-ChildItem .\extracted -Recurse
```

### 5. Read `flag.txt`
If it is directly inside the destination folder:

```powershell
Get-Content .\extracted\flag.txt
```

If it is nested in a subfolder, use the path shown by `Get-ChildItem`.

If extraction fails, verify that the file is a valid ZIP archive and inspect it with a suitable archive tool. A filename extension alone does not guarantee format.

## Result / Flag
**Pending verification.** The challenge indicates that the archive contains `flag.txt`, but the actual flag should be recorded only after successfully extracting and reading the file.

## What I Learned
- File extensions are labels and do not prove the underlying format.
- Magic bytes provide evidence about a file's structure.
- `Format-Hex` displays binary data in hexadecimal.
- Renaming a file does not convert it.
- Archive tools can extract files stored inside a ZIP archive.

## Security Note
Treat unexpected files from unknown sources cautiously. File-type validation should examine contents rather than trusting extensions alone.
