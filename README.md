# knot
Kabob Naming of Things (KNoT)

# Introduction 

This is a naming specification (kabob-style); to name really any information object, like: files, directories, computers, domain, etc. There will be scripting tools here to generate names for you. For now, there is a specification for reference, so you can create names on your own.

# Getting Started

## Installation

Simply clone this repository down, or for now, keep a link to the specification as reference.

# File naming convention

As a primer, let's dive into generating names for things; an excerpt from the specification:

## 1.1.2 Files
A general naming scheme for things will be in the following format, below. Naming will use the kabob form for ease of typing (e.g. first-second-last) with no spaces to ensure compatibility with operating systems. This format is general, and used when no dictating context exists.

> [!NOTE]
> Spaces are used for explanation purposes, and not used in the actual name.

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


> [!TIP]
> Category along with many of these parts are optional
> Descriptors are optional and are for differentiating with standout conditions, or attributes (e.g. blue, reversed, left, withborder, nocolor, pending, empty, … )
