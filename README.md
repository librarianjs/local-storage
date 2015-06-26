# Librarian Local Storage

## Installation
```
$ npm install librarian-local-storage
```

## Usage
```js
var express = require( 'express' )
var librarian = require( 'librarian' )
var LocalStorage = require( 'librarian-local-storage' )
var storage = new LocalStorage({
  // Where are these images stored?
  files: '/uploads', // optional, defaults to $PWD/files
})

var app = express()
app.use( '/files', librarian({
    storageEngine: storage
}) )

app.listen( 8888, function(){
    console.log( 'app listening' )
})
```

## Note

LocalStorage is the default storage engine used for librarian out of the box. If you do not specify otherwise, a directory called 'files' will be created and used in the the current working directory.

## Note

LocalStorage will attempt to create the directory given, but will continue whether this succeeds or fails.
If you need special permissions on this directory, ensure it is created ahead of time.
