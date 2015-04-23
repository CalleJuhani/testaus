.. code:: robotframework

	*** Settings ***        
	Suite Setup  Open Browser To Toolbar
	Suite Teardown  Close Browser
	Resource  resource.txt

Janne Heikkinen

Introduction
------------------------

Our user is a 40 year old dude who wants to share a bunch of his links to a friend. He has googled stuff and decides to try toolbar.


Log in
------------------------

First our user logs in with credentials he has created before and goes to the main page

.. code:: robotframework

	*** Test Cases ***
	User Should Be Able To Login With Valid Credentials
		Open Log In Dialog
		Type Valid Credentials
		Click Log In
	
	User Should Be Able To Navigate To The Actual Toolbar
		Go To Toolbar From Opening Page

Delete and create tab
------------------------

Now user would like to add two links to sites he likes to visit. First he deletes the example tab and creates a new tab for himself

.. code:: robotframework
	
	*** Test Cases ***
	User Should Be Able To Delete Tab
		Delete First Tab
	
	User Should Be Able To Create New Tab
		Create New Tab	Minun tabi


------------------------

Then he would like to add the links he wants to share

.. code:: robotframework

	*** Test Cases ***
	User Should Be Able To Add Links To Active Tab
		Click First Tab Active
		Add Link	Google	www.google.fi	Suosittu hakukone
		Add Link	Bing	www.bing.com	Vähemmän suosittu hakukone


Almost done! Now all he has to do is save the toolbar and log out

.. code:: robotframework

	*** Test Cases ***
	User Should Be Able To Save Toolbar
		Click Save Toolbar
		View Toolbar
		Log Out
		
