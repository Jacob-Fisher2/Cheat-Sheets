# Volatility 3 Common Commands

## OS Info
```vol.py -f “/path/to/file” windows.info```

Includes x32/x64 determination, major and minor OS versions, and kdbg information

## Process Information
### PSList
```vol.py -f “/path/to/file” windows.pslist```

```vol.py -f “/path/to/file” windows.psscan```

```vol.py -f “/path/to/file” windows.pstree```

```vol.py -r csv -f “/path/to/file” windows.pstree > pstree.csv```

Saves the output in CSV format so we can analyze it in Excel


### Procdump
```vol.py -f “/path/to/file” -o “/path/to/dir” windows.dumpfiles ‑‑pid <PID>```

Dumps exe and associated DLLs


### Memdump
```vol.py -f “/path/to/file” -o “/path/to/dir” windows.memmap ‑‑dump ‑‑pid <PID>```


### Handles
```vol.py -f “/path/to/file” windows.handles ‑‑pid <PID>```

PID, process, offset, handlevalue, type, grantedaccess, name


### Dlls
```vol.py -f “/path/to/file” windows.dlllist ‑‑pid <PID>```

PID, process, base, size, name, path, loadtime, file output


### cmdline
```vol.py -f “/path/to/file” windows.cmdline```


PID, process name, args

## Network Information
### Netscan
```vol.py -f “/path/to/file” windows.netscan```

```vol.py -f “/path/to/file” windows.netstat```


## Registry
### Hivelist
```vol.py -f “/path/to/file” windows.registry.hivescan```

```vol.py -f “/path/to/file” windows.registry.hivelist```


### Printkey
```vol.py -f “/path/to/file” windows.registry.printkey```

```vol.py -f “/path/to/file” windows.registry.printkey ‑‑key “Software\Microsoft\Windows\CurrentVersion”```


## Files
### File scan
```vol.py -f “/path/to/file” windows.filescan```


### Filedump
```vol.py -f “/path/to/file” -o “/path/to/dir” windows.dumpfiles```

```vol.py -f “/path/to/file” -o “/path/to/dir” windows.dumpfiles ‑‑virtaddr <offset>```

```vol.py -f “/path/to/file” -o “/path/to/dir” windows.dumpfiles ‑‑physaddr <offset>```


## Miscellaneous
### Malfind
```vol.py -f “/path/to/file” windows.malfind```

PID, process name, process start, protection, commit charge, privatememory, file output, hexdump disassembly


### Yarascan
```vol.py -f “/path/to/file” windows.vadyarascan ‑‑yara-rules <string>```

```vol.py -f “/path/to/file” windows.vadyarascan ‑‑yara-file “/path/to/file.yar”```

```vol.py -f “/path/to/file” yarascan.yarascan ‑‑yara-file “/path/to/file.yar”```

