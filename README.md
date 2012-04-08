# Binary file parser

Worst. Project name. Ever.

## What?

Yeah, basically, you create a file upload form element, and attach the BinaryFileUploader object to it, then when a user selects a file, it will parse it and generate a bytecode table for it, without ever making a request to the server.

## Why?

Mostly for the lulz, but I also want to create an emulator at some point, and need a way for user's to load up binary files, and this seemed like the most user friendly way of doing it.

## How?

1. Attach the binaryfileload.js and binarystring.js files to your page.
2. Once the page has loaded create a new instantiation of the BinaryFileUploader. The first argument is an object with the following items:
   * `element` The file upload element
   * `onFileLoad` A closure that is executed once the file is been loaded

   `onFileLoad` has one argument passed to it: a `BinaryString` object.

   eg:

       var uploader = new BinaryFileUploader({
		   element:    document.getElementById('file-input'),
		   onFileLoad: function(file) {console.log(file.toUtf8());}
	   });

3. Manipulate your `BinaryString` object as you see fit. Additional methods soon for dealing with integers, floats, more string formats

### Using `BinaryString` as a standalone object

You can use `BinaryString` on it's own, without using the `BinaryFileUploader`. Doing so is simple:

    var string = new BinaryString('binary data here');

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
