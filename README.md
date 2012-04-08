# Binary file parser

Worst. Project name. Ever.

## What?

Yeah, basically, you create a file upload form element, and attach the BinaryFileUploader object to it, then when a user selects a file, it will parse it and generate a bytecode table for it, without ever making a request to the server.

## Why?

Mostly for the lulz, but I also want to create an emulator at some point, and need a way for user's to load up binary files, and this seemed like the most user friendly way of doing it.

## How?

Using javascript's new FileReader api. It's pretty rad, and pretty easy.

- - -

## TODO

* Better documentation
* New functions:
  * Methods to parse signed/unsigned int's
  * Methods for floats
  * Utf16 and 32
* Muli file upload
* Drag+drop upload
* Tests
* Breaking large data sets in to smaller chunks
* Lazy loading of bytecode array?
* onProgress event
