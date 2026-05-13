# Windows `attrib` Cheat Sheet

## Syntax

```cmd
attrib [+flag|-flag] file [/s] [/d]
```

---

# Important Flags

| Flag | Meaning                 |
| ---- | ----------------------- |
| `+h` | hide file               |
| `-h` | unhide file             |
| `+r` | set read-only           |
| `-r` | remove read-only        |
| `+s` | set system attribute    |
| `-s` | remove system attribute |
| `+a` | set archive attribute   |

---

# Important Options

| Option | Meaning            |
| ------ | ------------------ |
| `/s`   | include subfolders |
| `/d`   | include folders    |

---

# Common Examples

## Show hidden files

```cmd
attrib -h file.txt
```

## Hide file

```cmd
attrib +h secret.txt
```

## Remove read-only

```cmd
attrib -r file.txt
```

## Unhide everything on USB drive

```cmd
attrib -s -h -r E:\*.* /s /d
```

## Show attributes

```cmd
attrib file.txt
```

## Hide folder

```cmd
attrib +h folder
```

## Make file system file

```cmd
attrib +s boot.ini
```

---

# Attribute Letters

| Letter | Meaning   |
| ------ | --------- |
| `H`    | Hidden    |
| `R`    | Read-only |
| `S`    | System    |
| `A`    | Archive   |

Example:

```cmd
A SHR secret.txt
```
