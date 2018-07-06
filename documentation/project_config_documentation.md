Project Configuration
==========

This configuration file will be used by Translation recorder to build the hierarchal structure of the project

A project hierarchy is separated into different levels each one contain a list of item within it. These items are things such as chapter with in a book or books within an anthology. By creating a hierarchy of between these items it allows TR to provide easy and efficient project set-up based on a specific set of specifications.

A simple example of what the hierarchy could look like:

	Bible/
    	|-Anthology/
        	|-Book/
            	|-Chapter/
                |-Chapter/
            |-Book/
            	|-Chapter
            |-Book/
            	|-Chapter/
                |-Chapter/
        |-Anthology/
        	|-Book/
            	|-Chapter/
                |-Chapter/
                |-Chapter/
            |-Book/
            	|-Chapter/
                |-Chapter/
	

Item Structure
-----------

Each item has a structure as follows:

    {
    	"localization": ""
    	"media": ""
  		"label": "",
  		"title": "",
 		"identifier": "",
  		"sort": "",
        "contains": [
        	...
        ]
    }

- ``localization``: Only used at the top-level of the hierarchy, used to reference the localization folder for this project
- ``media``: Is where any image or associated media with this item is stored if any
- ``label``: Describes what type this item is
- ``title``: Is the name of the item 
- ``identifier``: Is an identifier for the item if any
- ``sort``: Is the imposed order of the items within this level
- ``contains``: A list of everything within the level underneath the current item if any.

Example Project_Config File
---------------
	{
  		"localization": "./localization",
  		"media": "./media/door43_bible.png"
  		"label": "Bible",
  		"title": "Bible",
  		"sort": "1",
  		"contains": [
    	{
      		"media": "./media/door43_old_testament.png"
      		"label": "Anthology",
      		"title": "Old Testament",
      		"identifier": "OT",
      		"sort": "1",
      		"contains": [
        	{
          		"media": "./media/door43_genesis.png"
          		"label": "Book",
          		"title": "Genesis",
          		"identifier": "Gen",
          		"sort": "1",
          		"contains": [
            	{
              		"label": "Chapter",
              		"title": "Genesis 1",
              		"identifier": "Gen 1",
              		"sort": "1"
            	}]
        	}]
    	}]
	}

