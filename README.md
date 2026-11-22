# extISO

A small Win32 utility for extracting files from `.iso` images into a target directory.

Instead of relying on third-party parsing libraries (like 7-Zip or libarchive), `extISO` uses the native Windows Virtual Disk API (`VirtDisk.dll`) — the exact same subsystem Windows Explorer uses when you double-click to mount an ISO. It temporarily attaches the image, copies the contents, and cleanly detaches it.

## Features

- **Native Mounting:** Uses standard Win32 Virtual Storage APIs (`OpenVirtualDisk`, `AttachVirtualDisk`, etc.) for full UDF/ISO9660 compatibility.
- **Standalone:** Single `.exe` with no external DLL dependencies or installation required.
- **Clean:** Automatically detaches the virtual drive once extraction finishes or if an error occurs.

## Download

Grab the latest binary from the [Releases](../../releases) tab.

*Note: Since the binary is not signed with an EV code signing certificate, Windows SmartScreen or Defender may show a warning on first run.*

## Usage

**GUI:**
Run `extISO.exe`, select the `.iso` file, pick the output directory, and hit Extract.

## Requirements

- Windows 8 / 10 / 11 (x86 or x64). Windows 7 is not supported as native ISO mounting via `VirtDisk` was introduced in Windows 8.
- Administrator privileges may be required depending on your system's virtual disk policy.

## License

Freeware. The binary is free to use and redistribute as-is, though the source code is currently closed.
