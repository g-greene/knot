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
#### 1.1.1 Folders
Folder (directory) structures, or patterns, for organizing files are outlined below, on the next page. Folder names are to be short, in kabob form, no spaces, and nested from most general to specific. 
NOTE: Since folders set the context, they in turn affect the names of the files that fall underneath. With that, containing scopes, or category names may not be needed in the file name.

Working artifacts pattern – for artifacts via running services and applications
	[top-level scope]
|- archive (processed artifacts)
(same structure as ‘working’)
|- failed (failed-to-be-processed artifacts)
(same structure as ‘working’)
|- log (activity logs for artifact creation and processing)
|- [yyyymmdd]
|- [yyyymmddhh].log
| - (n, …)
| - (n, …)
|- working  (created artifacts; unprocessed)
|- [artifacts scope]
|- [category]
|- (n, …)
|- [artifact name]
|- (n, …)
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
	



Support artifacts pattern – a static pool of integrative artifacts (for quick use, project support)
	[top-level scope]
|- assets  (single resource files)
|- [category]
|- (n, …)
|- [sub category] (optional)
|- [artifact name]
|- (n, …)
|- templates (complex multifile archives / multipart project files)
|- [category]
|- (n, …)
|- [sub category] (optional)
|- [artifact name]
|- (n, …)
|- settings  (single files containing application settings)
|- [category]
|- (n, …)
|- [sub category] (optional)
|- (n, …)
|- [artifact name]
|- (n, …)

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

	






1.1.2 Files
A general naming scheme for things will be in the following format, below. Naming will use the kabob form for ease of typing (e.g. first-second-last) with no spaces to ensure compatibility with operating systems. This format is general, and used when no dictating context exists. 
NOTE: spaces are used for explanation purposes, and not used in the actual name.

	
[containing scope] - [category] - [subject] - [1° descriptor] - [2° desc.] (3°, n ...)

e.g.  xyzcompany-accounting-salesorder-3488831-amended

For sequential naming, a date or datetime can precede the containing scope:
	
[yyyymmdd] - [containing scope] - [category] - [subj.] - [1° descriptor] - [2° desc.] (3°, n ...)

e.g.  20231201-xyzcompany-accounting-salesorder-3488831-amended

	
NOTE: other sequencers should be at the front of the name as well, for filesystem sorting. e.g. order numbers


With a datetime, [yyyymmddhhmmssSS]
	
e.g.  2023120112051101-xyzcompany-accounting-salesorder-3488831-amended


	
•	Category along with many of these parts are optional
•	Descriptors are optional and are for differentiating with standout conditions, or attributes (e.g. blue, reversed, left, withborder, nocolor, pending, empty, … )




1.2 Filesystem object naming and their contexts
1.2.1 Order Files
1.2.1.1 Business Central
1.2.1.1.1 JSON
1.2.1.1.2 FTP
1.2.1.2 Fastrax

1.2.2 Tax Right Files 
INPUT
OUTPUT

1.2.2 Developing applications
1.2.2.1 General

1.3 Software represented objects and their contexts
1.3.1 Administrative
1.3.1	Software represented objects and their contexts 
1.3.2	Administrative
1.3.2.1	General
1.3.2.2	Organizational units
1.3.2.3	Computers
1.3.2.3.1	
1.3.2.4	Database objects
