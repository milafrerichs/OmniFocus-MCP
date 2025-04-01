# OmniFocus MCP Server

A Model Context Protocol (MCP) server that integrates with OmniFocus to enable Claude to interact with your tasks and projects.

## Quick Start

## Overview

## Features


## Installation

1. Clone this repository
2. Install dependencies:

```bash
npm install
```

3. Build the project:

```bash
npm run build
```



## Running the Server

Start the MCP server:

```bash
npm start
```

The server will run on http://localhost:3000 by default. You can change the port by setting the PORT environment variable.



# Relevant Omnifocus API Docs
complete docs are found at `omnifocus_api_complete.txt`

OmniFocus 3.13.1 (v151.27.0)

Core Server-Relevant Classes:

Application
Instance Functions
function openDocument(from: Document or null, url: URL, completed: Function(‍documentOrError: Document or Error, alreadyOpen: Boolean‍))
Attempts to open the specified document and return a reference to it asynchronously.

Instance Properties
var buildVersion → Version read-only
var name → String read-only
var platformName → String read-only
var userVersion → Version read-only

Database
Instance Functions
function tagNamed(name: String) → Tag or null
function folderNamed(name: String) → Folder or null
function projectNamed(name: String) → Project or null
function save()
function moveTasks(tasks: Array of Task, position: Project, Task, or Task.ChildInsertionLocation)
function duplicateTasks(tasks: Array of Task, position: Project, Task, or Task.ChildInsertionLocation) → TaskArray
function convertTasksToProjects(tasks: Array of Task, position: Folder or Folder.ChildInsertionLocation) → Array of Project
function moveSections(sections: Array of Project or Folder, position: Folder or Folder.ChildInsertionLocation)
function duplicateSections(sections: Array of Project or Folder, position: Folder or Folder.ChildInsertionLocation) → SectionArray
function moveTags(tags: Array of Tag, position: Tag or Tag.ChildInsertionLocation)
function duplicateTags(tags: Array of Tag, position: Tag or Tag.ChildInsertionLocation) → TagArray
function cleanUp()
function undo()
function redo()
function deleteObject(object: DatabaseObject)

Instance Properties
var flattenedFolders → FolderArray read-only
var flattenedProjects → ProjectArray read-only
var flattenedTags → TagArray read-only
var flattenedTasks → TaskArray read-only
var folders → FolderArray read-only
var inbox → Inbox read-only
var library → Library read-only
var projects → ProjectArray read-only
var settings → Settings read-only
var tags → Tags read-only

Task
Instance Functions
function taskNamed(name: String) → Task or null
function addTag(tag: Tag)
function addTags(tags: Array of Tag)
function removeTag(tag: Tag)
function removeTags(tags: Array of Tag)
function clearTags()
function markComplete(date: Date or null) → Task
function markIncomplete()
function drop(allOccurrences: Boolean)

Instance Properties
var name → String
var note → String
var completed → Boolean read-only
var completionDate → Date or null read-only
var deferDate → Date or null
var dropDate → Date or null read-only
var dueDate → Date or null
var estimatedMinutes → Number or null
var flagged → Boolean
var sequential → Boolean
var tags → TagArray read-only
var taskStatus → Task.Status read-only

Project : DatabaseObject
Instance Functions
function taskNamed(name: String) → Task or null
function markComplete(date: Date or null) → Task
function markIncomplete()
function addTag(tag: Tag)
function addTags(tags: Array of Tag)
function removeTag(tag: Tag)
function removeTags(tags: Array of Tag)
function clearTags()

Instance Properties
var name → String
var completed → Boolean read-only
var completionDate → Date or null
var deferDate → Date or null
var dropDate → Date or null
var dueDate → Date or null
var estimatedMinutes → Number or null
var flagged → Boolean
var sequential → Boolean
var status → Project.Status
var tags → TagArray read-only
var tasks → TaskArray read-only

Tag : ActiveObject
Instance Functions
function tagNamed(name: String) → Tag or null
function apply(function: Function) → ApplyResult or null

Instance Properties
var name → String
var status → Tag.Status
var tasks → TaskArray read-only

Settings
Settings represent the database synchronized configuration values.

Instance Functions
function defaultObjectForKey(key: String) → Object or null
function hasNonDefaultObjectForKey(key: String) → Boolean
function objectForKey(key: String) → Object or null
function setObjectForKey(value: Object or null, key: String)
function boolForKey(key: String) → Boolean
function setBoolForKey(value: Boolean, key: String)
function integerForKey(key: String) → Number
function setIntegerForKey(value: Number, key: String)

URL.FetchRequest/Response
For making HTTP requests and handling responses.

Timer
For scheduling tasks.

Version
For version comparison and management.

Credentials
For secure storage of sensitive information.

Console
For logging and debugging.