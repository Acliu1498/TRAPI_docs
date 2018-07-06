 .. WA Backend documentation master file, created by
   sphinx-quickstart on Fri Jul  6 13:35:46 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to WA Backend's documentation!
======================================

.. toctree::
   :maxdepth: 2
   :caption: Contents:

Project Configuration
=====================

This configuration file will be used by Translation recorder to build the hierarchal structure of the project

A project hierarchy is separated into different levels each one contain a list of item within it. These items are things such as chapter with in a book or books within an anthology. By creating a hierarchy of between these items it allows TR to provide easy and efficient project set-up based on a specific set of specifications.

Here is a simple example of what the hierarchy could look like:

.. code-block::

	|-- Bible
    	|-- Anthology
    		|-- Book
        		|-- Chapter
            	|-- Chapter
        	|-- Book
        		|-- Chapter
	        |-- Book
	        	|-- Chapter
	            |-- Chapter
        |-- Anthology
        	|-- Book
            	|-- Chapter
                |-- Chapter
                |-- Chapter
            |-- Book
            	|-- Chapter
                |-- Chapter


Item Structure
--------------

Each item or level in the hierarchy can have the following keys:

* ``localization`` Only used at the top-level of the hierarchy and references the localization folder for this project.

	* The localization properties files should be stored in this location. Each localized file should be named ``yourResourceName_languageslug.properties`` (e.g., ``door43_es.properties`` for the Door43 project localization file for Spanish)

* ``media``: Provides the path to any media that should be associated with this level
* ``label``: Type of this item is (e.g., ```book``). Note that this value should not be the literal string, but the name of the property in the localization files
* ``title``: Name of the item (also localized like ``label``)
* ``identifier``: An identifier for the item if any
* ``sort``: Is the imposed order of the items within this level
* ``contains``: Either a list of child items, a single child item, or a path to a secondary JSON file containing the child items.

Example ``project_config.json`` File
------------------------------------
::

 {
                "media": "./media/door43_old_testament.png"
                "label": "anthology",
                "title": "oldTestament",
                "identifier": "bible-ot",
                "sort": "1",
                "contains": [
                {
                        "media": "./media/door43_genesis.png"
                        "label": "book",
                        "title": "genesis",
                        "identifier": "gen",
                        "sort": "1",
                        "contains": [
                {
                        "label": "chapter",
                        "title": "genesis01",
                        "identifier": "gen01",
                        "sort": "1"
                }]
                }]
        }]
   }


Chunks
======

Each project is separated into smaller chunks, which the user records. The recorded chunks are later put together to create the finished project. Each chunk requires the following:

- ``start``: the beginning unit number of the chunk

- ``end``: the end unit number of the chunk

- ``sort``: the chunk number

The default chunk is one unit of the smallest division of the source text (e.g. the smallest division of the Bible is verses, so the default chunk would be one verse).

**Example chunks.json file:**

.. code-block:: yaml

    {

      "chunks": [{

                     start: 1

                     end: 1

                     sort: 1

                 },

                 {
                     start: 2

                     end: 2

                     sort: 2

                 },

                 {
                    start: 3

                     end: 3

                     sort: 3

                 }]

    }




Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
