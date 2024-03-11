# Kabob Naming of Things (KNoT)
## Release
Draft April 27th 2023
## Author
Greg Greene
## Abstract
This draft specification outlines a kabob-based nomenclature and organizing structures generally for internal and external IT related objects. Such objects include: organizational units, relational database objects, computers, filesystem objects, software code data structures, and domain (host) names. 

## Table of Contents
1.	Overview of the nomenclature for things
- 1.1.	General naming schemes
    - 1.1.1.	Folders
    - 1.1.2.	Files
- 1.2.	 Filesystem object naming and their contexts
    - 1.2.1.	Order files and folders
      - 1.2.1.1.	Dynamics Business Central
      - 1.2.1.2.	Incoming orders from customers
    - 1.2.2.	Developing applications
      - 1.2.2.1.	General
      - 1.2.2.2.	Assets
      - 1.2.2.3.	Source code files
- 1.3.	Software-managed objects and their contexts 
    - 1.3.1.	Administrative
      - 1.3.1.1.	General
      - 1.3.1.2.	Entra (Azure AD) groups
      - 1.3.1.3.	Computers
      - 1.3.1.4.	Database objects


## 1 Overview of the nomenclature for things
### 1.1 General naming schemes
## 1.1.1 Folders
Folder (directory) structures, or patterns, for organizing files are outlined below, on the next page. Folder names are to be short, in kabob form, no spaces, and nested from most general to specific. 
> [!NOTE]
> Since folders set the context, they in turn affect the names of the files that fall underneath. With that, containing scopes, or category names may not be needed in the file name.
> 

1. **`Working artifacts pattern` – for artifacts via running services and applications**
	- [top-level scope]
		- |- **`archive`** (processed artifacts)
			- _(same structure as ‘working’)_
		- |- **`failed`** (failed-to-be-processed artifacts)
			- _(same structure as ‘working’)_
		- |- **`log`** (activity logs for artifact creation and processing)
			- |- [yyyymmdd]
				- |- [yyyymmddhh].log
				- |- _(n, …)_
			- |- _(n, …)_
		- |- **`working`**  (created artifacts; unprocessed)
			- |- [artifacts scope]
				- |- [category]
				- |- _(n, …)_
					- |- [artifact name]
					- |- _(n, …)_
```
e.g. 
the-business-application
	|- archive
	|- failed (failed-to-be-processed artifacts)
	|- log
		|- 20230428
			|- 2023042815.log
	|- working
		|- orders
			|- customer-abc
				|- 2023120112051101-order.json
```	



1. **`Support artifacts pattern` – a static pool of integrative artifacts (for quick use, project support)**
	- [top-level scope]
		- |- **`assets`**  (single resource files)
			- |- [category]
				- |- _(n, …)_
				- |- [sub category] _(optional)_
					- |- [artifact name]
						- |- _(n, …)_
		- |- **`templates`** (complex multifile archives / multipart project files)
			- |- [category]
				- |- _(n, …)_
				- |- [sub category] _(optional)_
					- |- [artifact name]
						- |- _(n, …)_
		- |- **`settings`**  (single files containing application settings)
			- |- [category]
				- |- _(n, …)_
				- |- [sub category] _(optional)_
					- |- _(n, …)_
					- |- [artifact name]
						|- _(n, …)_
```
e.g. 
 design-resources
	|- assets
		|-  raster
			|-  face-smiley-background-blue.png
	|- templates
		|-  word
			|-  letter-introduction-formal.docx
	|- settings
		|-  photoshop
			|-  fileformats
				|-  autocad.8bi
```

## 1.1.2 Files
A general naming scheme for things will be in the following format, below. Naming will use the kabob form for ease of typing (e.g. first-second-last) with no spaces to ensure compatibility with operating systems. This format is general, and used when no dictating context exists. 
NOTE: spaces are used for explanation purposes, and not used in the actual name.

### General example

> **[containing scope] - [category] - [subject] - [1° descriptor] - [2° desc.] (3°, n ...)**
> 
> e.g.  xyzcompany-accounting-salesorder-3488831-amended
> 

### For sequential naming, a date or datetime can precede the containing scope:

> **[yyyymmdd] - [containing scope] - [category] - [subj.] - [1° descriptor] - [2° desc.] (3°, n ...)**
>
> e.g.  20231201-xyzcompany-accounting-salesorder-3488831-amended
> 

> [!NOTE]
> Other sequencers should be at the front of the name as well, for filesystem sorting. e.g. order numbers

### With a datetime:

> **[yyyymmddhhmmssSS]**
>
> e.g.  2023120112051101-xyzcompany-accounting-salesorder-3488831-amended


> [!NOTE]
> Category along with many of these parts are optional
> Descriptors are optional and are for differentiating with standout conditions, or attributes (e.g. blue, reversed, left, withborder, nocolor, pending, empty, … )


## 1.2 Filesystem object naming and their contexts
### 1.2.1 Order Files
#### 1.2.1.1 ERP system
##### 1.2.1.1.1 JSON
##### 1.2.1.1.2 FTP
#### 1.2.1.2 Retail Software
### 1.2.2 Tax Files 
### 1.2.2 Developing applications
#### 1.2.2.1 General
## 1.3 Software represented objects and their contexts
### 1.3.1 Administrative
### 1.3.1 Software represented objects and their contexts 
### 1.3.2 Administrative
#### 1.3.2.1 General
#### 1.3.2.2 Organizational units
#### 1.3.2.3 Computers
## 1.3.2.4 Database objects
Database table, view, function, and procedure naming is determinate by the database they're in (whether the database is for a specific app, or is all inclusive). Some context examples are:

> [!NOTE]
> Database names and identifiers can require [0-9a-zA-Z_@#] as outlined in [SQL Server: Database identifiers](https://learn.microsoft.com/en-us/sql/relational-databases/databases/database-identifiers?view=sql-server-2017#rules-for-regular-identifiers),
> so we'll use the "dropped kabob" or snake case here.
>

### `Routine - Database: all inclusive`

> **[company] _ [app name] _** _[routine type]_ **_ [db object] _ [activity] _** _[revision]_
>
> e.g.
> kabobcorp_numbercruncher_expenses_updatetotals
> 
> **_(or)_**
>
> kabobcorp_numbercruncher_sp_expenses_updatetotals __20240210_
> 

### `Routine - Database: single app`

> _[routine type]_ **_ [db object] _ [activity] _** _[revision]_
>
> e.g.
> expenses_updatetotals
> 
> **_(or)_**
> 
> sp_expenses_updatetotals_r9

### `Table - Database: all inclusive`

> **[company] _ [app name] _** _[table type]_ **_ [name] _** _[revision]_
>
> e.g.
> kabobcorp_numbercruncher_expense
> 
> **_(or)_**
>
> kabobcorp_numbercruncher_table_expense __20240210_
> 

### `Table - Database: single app`

> _[table type]_ _ **[name] _** _[revision]_
>
> e.g.
> account_types
> 
> **_(or)_**
>
> picklist_account_types __20240210_

> [!NOTE]
> It's possible to use a table type, in table names to reduce the burden of remembering the purpose or general structure of the table.
> Some possibilities are: link, table, picklist, dump.
>

### General table structures

> [!TIP]
> If you're looking for patterned table structures, in "dropped-kabob" form, you might use these. They meet a variety of requirements, with metadata fields included.

### `Table: general entity`

- [x] :key: id (uuid) - _primary key_
- [ ] code (nvarchar) - _a unique code for reference_
- [ ] name (nvarchar)
- [ ] version_number (int) - _an incrementing value_
- [ ] created_by (uuid) 
- [ ] created_on (datetime)
- [ ] created_on_behalf_by (uuid)
- [ ] modified_by (uuid)
- [ ] modified_on (datetime)
- [ ] modified_on_behalf_by (uuid)
- [ ] utc_time_zone_offset (int)

### `Table: link`

- [x] :key: table_a_table_b_id (uuid) - _primary key_
- [x] :key: table_a_id (uuid)
- [x] :key: table_b_id (uuid)
- [ ] code (nvarchar) - _a unique code for reference_
- [ ] version_number (int) - _an incrementing value_
- [ ] created_by (uuid) 
- [ ] created_on (datetime)
- [ ] created_on_behalf_by (uuid)
- [ ] modified_by (uuid)
- [ ] modified_on (datetime)
- [ ] modified_on_behalf_by (uuid)
- [ ] utc_time_zone_offset (int) 
