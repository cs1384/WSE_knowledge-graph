WSE_knowledge-graph
===============

crawled more than 7 million wikipedia pages, extracted relations from infobox, tables and lists to get the knowledge of entities. User will be able to search with semi-structured query and get something like the infobox given by Google when you are searching a popular query.

===============
Usage:

Download this project. Unzip it, move under the directory and create a new folder names g16

$ cd WSE_project && mkdir g16

Download lib.zip from from https://www.dropbox.com/sh/gz325n1ye50556s/AACXOZHV5MRABZllSWzjRolRa?dl=0, unzip it and put the lib folder along with /src

$ find . -name '*.java' | xargs javac -cp lib/commons-io-2.4.jar:lib/jsoup-1.8.1.jar:lib/stanford-corenlp-3.5.0-models.jar:lib/stanford-corenlp-3.5.0.jar:lib/gson-2.3.1.jar:lib/java-json.jar:lib/wikixmlj-r43 -d g16

$ cd g16 && mkdir data

To parse the raw corpus, you have to download corpus_cache.zip from https://www.dropbox.com/sh/gz325n1ye50556s/AACXOZHV5MRABZllSWzjRolRa?dl=0, unzip it and put the corpus_cache folder under /data 

$ java wseproject.Tester2

To directly use parsed relations, download relations.zip from https://www.dropbox.com/sh/gz325n1ye50556s/AACXOZHV5MRABZllSWzjRolRa?dl=0, unzip it and put the relations folder under /data

$ java wseproject.server.KGServer

To allow web interface, download web.zip from https://www.dropbox.com/sh/gz325n1ye50556s/AACXOZHV5MRABZllSWzjRolRa?dl=0, unzip it and put the web folder under /data and put "http://localhost:25816/knowledge" in browser to start off

$ curl "http://localhost:25816?query=capital+of+venezuela"
$ curl "http://localhost:25816?entity=karachi&property=population"
