Noted
======
by Josh Panter: http://unfettered.net

A secure PHP based Web App for reading either Gnote or Tomboy Notes.

###TODO (in almost no particular order): 

1. Move all config variables to a single file and add accessible user customization
2. Add arbitrary note sharing via url with and/or without auth (ie., anonymous users can still see notes if they have direct url access)
3. Add built in url shortenr for above feature
4. Add honeypot options (see project honeypot https://www.projecthoneypot.org/)
5. Add notebooks
6. Add translations
7. Add ability to sort notes via name and date of creation and/or last edit
8. Exclude template files

###SETUP - this setup assumes that your webserver is apache

1. Copy the Noted main folder (this repository) to your web server. See the provided alias example (noted.conf) to put this in the web path.

2. Get Gnote/Tomboy noted into the path of Noted. There are two ways to do this.

	2a. Link Tomboy Notes' or Gnote's actual note folder as a folder named 'notes' to main folder. If you do this.

For Gnote this will be ` ~/.local/share/gnote `
For Tomboy this will be ` ~/.local/share/tomboy `

```bash
$ cd /path/to/noted
$ ln -s ~/.local/share/gnote notes
```

	2b. Open "assets/noted.php" in your favorite text editor and alter the $APP_PATH setting on line 04 from "notes" to "/home/YOUR_USER_NAME/.local/share/gnote" (or tomboy, respectively).

3. Make certain that www-data is a member of the YOUR_USERNAME group, and then check your work by executing:

```bash
$ usermod -a -G YOUR_USERNAME www-data
$ groups www-data
```

4. Make certain that 750 permissions are set on  ` ~./.local`  ` ~./.local/share` and ` ./.local/share/gnote`
 
```bash
$ chmod 750 ~./.local
$ chmod 750 ~./.local/share
$ chmod 750 ~./.local/share/gnote -R
```
5. Set optional variables in assets/noted.php

	a. set auth to true (and follow further instructions in that file) if you want to secure your Noted Web App
	b. add a personal greeting

###CREDITS
Scripts used for inspiration and/or copypasta:

1. https://wiki.gnome.org/Apps/Tomboy/UsageIdeas

2. https://github.com/gojigeje/tomboy-php

3. http://www.zubrag.com/scripts/

feedback is always welcome.
===========================

    Copyright (C) 2016 Josh Panter

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.