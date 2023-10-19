---

:warning: Please note that SP Reportify is actively in development, if you have ideas or encounter bugs, don't hesitate to create an issue!!

---

# SP Reportify

SP Reportify is a simple utility to create and run reports using data in a SharePoint Site.

SharePoint List Views are great to visualize the data from the List or Library.  Some key points always took me away from using them for users.  

# Features at a glance

- Datasource is not exposed: users cannot navigate elsewhere in the Site nor changing the List or Library View.

...


# Installation

## The Report List
You first need to create a new List, in the same site your datasources are.  The List should contains the following columns:

Column Title|Type
---|---
Title|Single line of text
Description|Multiple lines of text
ListId|Single line of text
SelectEntries|Multiple lines of text
ShowEntries|Multiple lines of text
SortEntries|Multiple lines of text
Query|Multiple lines of text

## Install the Package

1. Download the latest release from the [Releases](https://github.com/Dreller/DSP-Reporting/releases) page.
1. Extract the content on your computer.
1. Copy the file `bin/dconf.template.js`, rename to `bin/dconf.js`.  See the [Configuration file](configuration-file) to know how to set it up.
1. In your SharePoint Site, upload all files in a new Document Library or in a new Folder in an existing Library.

## Configuration File

The Configuration file is named `dconf.js`, under the `bin` folder.
It is a file that set global JavaScript variables, used by the main library, so you don't need to get in the big code file.

> :bulb: This file will be more detailled in the future, once all settings are identified and when the first real release will be published.

### Set the SharePoint Site URL

Variable `_URL` must be set to the root addess of the SharePoint site that contains your data.

### Set the SharePoint List Name where to store Reports

Variable `_REPORT_LIST` must contains the Name/Title of the SharePoint List where reports are saved.

---

**dconf.js**

```JavaScript
/**
 * Configuration File
 */

// SharePoint Site URL
var _URL = "https://123.sharepoint.com/sites/Mysite";

// List for saving Reports
var _REPORT_LIST = "Reports";

// Allow reporting on Libraries.
var _ALLOW_LIBRARY = false;

// Allow reporting on Hidden Libraries
var _ALLOW_LIBRARY_HIDDEN = false;

// Allow reporting on Lists.
var _ALLOW_LIST = true;

// Allow reporting on Hidden Lists
var _ALLOW_LIST_HIDDEN = false;

// Always-available Fields (columns) -> Array of "Name"
var _ALLOW_FIELDS_ALWAYS = ["ID"];

var _SPREPORTIFY_BUILDER_PAGE = "dbr.aspx";
var _SPREPORTIFY_RUNNER_PAGE = "drr.aspx";
```




## Download

Download the latest release from the [Releases](https://github.com/Dreller/DSP-Reporting/releases) page.



## License

TBD - Free to use, but do not rebrand and take ownership.  Nice features are comming in a near future.


---