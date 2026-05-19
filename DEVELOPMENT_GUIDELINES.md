# Xvolution Development Guidelines

This file is focusing on Blue Yonder Guidelines within Xvolution development. The goal of this document is to harmonize these guidelines and make them global for all Blue Yonder system landscapes. All guidelines must be considered for software development at Xvolution.

This guidelines contains:
- MOCA levels (.mlvl)
- MOCA local-syntax commands (.mcmd)
- Database DDL in `db/ddl`

## MOCA levels (.mlvl)
MOCA local-syntax commands are organized into multiple levels, each defined by a corresponding `.mlvl` file that outlines the structure and scope of that level. All MOCA commands for a given level must reside in a folder with the same name as the `.mlvl` file.

> **Note:** The `.mlvl` file must reside in the `src/cmdsrc` directory.

All the MOCA components developed by Xvolution must reside in the xvoint MOCA Level. 

> **File Location:** src/cmdsrc/xvoint.mlvl

```xml 
<component-level>
  <name>XVOint</name>
  <description>Xvolution MOCA Level</description>
  <package>net.xvolution.xvoint</package>
  <sort-sequence>10000</sort-sequence>
  <editable>true</editable>
</component-level>
```

> **Folder structure**

```text
/
└── src/
    └── cmdsrc/
        └── xvoint/
        └── XVOint.mlvl
```

## MOCA local-syntax commands (.mcmd) 

### Command Naming Convention

Command names follow a **verb/noun clause** structure:

- The **verb** defines the action.
- The **noun clause** specifies the target of the action and may include grammatical elements such as *an*, *a*, *for*, *the*, etc.

#### 🔹 Verb Clause Guidelines

- The verb must be a **single action word**.
- An embedded subsystem name prefix (e.g., `LS_`, `SL_`, `TM_`, `WM_`) **should NOT** be part of the verb, as the verb should be a proper **English action verb**.
- When creating a new component, developers should review and consider the **existing list of verbs** to maintain consistency and avoid duplication.
- Verbs carry the **same meaning across all MOCA applications** and should be reused when applicable.

> ✅ **Standard maintenance verbs have already been established** and should be used wherever relevant.

### 📘 Standard Verbs

| Verb     | Example Command                          |
|----------|------------------------------------------|
| `create` | `create usr cost center`                 |
| `change` | `change var waves not released`          |
| `remove` | `remove usr account number`              |
| `list`   | `list var bol data`                      |
| `get`    | `get usr label qty`                      |
| `set`    | `set var audit flag`                     |
| `produce`| `produce var lpn label`                  |
| `process`| `process var cartonization`              |

To prevent naming conflicts with standard commands in future releases, all **Xvolution custom commands** must strictly follow this naming convention.
