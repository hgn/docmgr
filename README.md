# docmgr

Convert automatically an project document tree versionied in git and writen in markdown
into a PDF document. Linked images are automatically inserted. This applies for PNG, GIF
and JPG as well as for SVG illustrations.

The consertion is started when a new markdown document is pushed into the repository.

The PDF document is added to the repository as soon it is generated. The name of the
document is identical to the source file name, except the file ending: .pdf.

Index generation. The backend will generate an hidden index file - at the top level of
the document root. This index file is encoded in JSON and contains all required information
to use it in third party search tools.



# Project Structure

Can be created, designed as required by project requirements. There is no pre-defined
schema. Anyway, there are some requirements required:

```
/templates/modern.tex
/templates/conservative.tex

/proctect-a/
/proctect-a/topic-aa/
/proctect-a/topic-aa/document.md
```

# Minimal Document

```
title: This is the Titel
subtitle: This is the sub title
template: modern
authors: [["Hagen Paul Pfeifer"], ["hagen@jauu.net"], ["John Doe"], ["john@example.com"]]
date: generation-date-full
toc: enable
fontsize: 12

```


# Index File Format

```
{
 "author" [
  {"name" : "Hagen Paul Pfeifer", "email" : "hagen@jauu.net", "docs" : [
     "/proctect-a/topic-aa/document.md",
     /proctect-a/topic-bb/document.md"
  ]
 }
 ],
 
 
  "last-modified" [
     [ "/proctect-a/topic-aa/document.md", 824838328 ],
     [ "/proctect-a/topic-bb/document.md", 934939349 ],
  ]
 ],
 
}
```
