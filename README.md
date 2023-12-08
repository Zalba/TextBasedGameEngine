# The Way Text Engine
Thank you for choosing The Way Text Adventure Game Engine!
The Way Text Adventure Game Engine is designed easily to run text-based games. 
This README Will guide you through the process for downloading and installing the Game Engine on Linux, as well as describing the syntax of Game file code, so you can make your own text-based game!
The following processes are commands that must be run in the Terminal
## Download and Installation
This is the process for downloading and installing all neccesary files.
### Install Java Compiler
Use these commands to install Java JDK, which the Engine requires to function
```
sudo apt install default-jdk
sudo apt install openjdk-11-jdk-headless
sudo apt install ecj
sudo apt install openjdk-8-jdk-headless
```
### Install Git and Repository
Use these commands to download and install The Engine from its Git Repository
```
sudo apt install git
git clone http://bitbucket.org/catricj/the_way/src/master ./home/The_Way
```
## Compiling and Running Game files
### Compile the Game Engine
Use this command to Compile the Engine
```
javac -cp ".:/home/your_user_name/The_Way/luaj-jme-3.0.1.jar:/home/your_user_name/The_way/luaj-jse-3.0.1.jar:/home/The_Way/jdom-2.0.6.jar" /home/The_Way/*.java
```
### Run the Game File
```
java -cp ".:/home/your_user_name/The_Way/luaj-jme-3.0.1.jar:/home/your_user_name/The_way/luaj-jse-3.0.1.jar:/home/The_Way/jdom-2.0.6.jar:/home/The_Way" Engine
```
## Game File Syntax
The following is the syntax of Game File XML. A markup block is required if it is designated with the "*" icon.
### Markup Block Types
*<Game></Game> - Game File Block. Everyhing must exist within this Game block
*<title></title> - Title. Gives the Title of the Game or The Room.
<d></d> - Description. Describes the Room or item as a String.
*<room id="ROOM_ID_NUMBER"></room> - Room block. Any Room descriptor must be within this block.
	<north>ROOM_ID_NUMBER</north> - Identifies the room to the north.
	<south>ROOM_ID_NUMBER</south> - Identifies the room to the south.
	<east>ROOM_ID_NUMBER</east> - Identifies the room to the east.
	<west>ROOM_ID_NUMBER</west> - Identifies the room to the west.
<item></item> - Item Block. Any Item descriptor must be within this block.
	<take>BOOLEAN</take> - Determines whether or not the item is able to be taken.
	<use></use> - Description of item when used. Item cannot be used if there is no <use>.
	<uscript>SCRIPT</uscript> - Allows a script file to be run if an item is used.
	<check></check> - Checks if item is in player's inventory.
### Generalized Game File 
```
*<Game>
	*<title>Game Title</title>
	*<room id="#">
		*<title>Room Title</title>
		<d>Room Description</d>
		<north>#</north>
		<south>#</south>
		<east>#</east>
		<west>#</west>
		<item>
			<title>Item Title</title>
			<d>Item Description</d>
			<take>true</take>
			<use>Use description</use>
			<uscript>Script.lua</uscript>
			<check></check>
		</item>
	</room>
</Game>
```