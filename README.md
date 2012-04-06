#POUCH - Penn cOUCHdb interface
###A pure C wrapper for working with CouchDB.

##Dependencies
Pouch depends on `libcurl` to perform HTTP requests. If you only need synchronous functionality, simply link with `-lcurl` at compile time.

For asynchronous functionality, Pouch depends on `libevent`. After installing, link with `-levent`. Synchronous requests will work perfectly without it.

##Compiling
Synchronous:

	gcc -o $program $program.c pouch.c -lcurl

Asynchronous:

	gcc -o $program $program.c pouch.c multipouch.c -lcurl -levent

to compile the example program, demo.c, which
uses an extension of Joseph Adams' [JSON library](http://git.ozlabs.org/?p=ccan;a=tree;f=ccan/json):

	make

##Description
A simple way to interact with CouchDB instances through low-level
CURL requests and the JSON library of your choice. 

##Features

* Two flavors: synchronous or asynchronous.
* Simple: already includes functions for the most common use cases.
* JSON Library-agnostic: use any JSON library you want, or use none at all. The basic functionality of Pouch doesn't depend on any particular JSON library. Use your favorite, roll your own, or build the strings by hand.
