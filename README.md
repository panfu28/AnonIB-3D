# AnonIB 3D by Alex Krunch / Forked by PVNFU
![Screenshot](https://pbs.twimg.com/media/D9Hjo53W4AUguEy.jpg)
This project is a prototype for a 3D anonymous imageboard.

## Software
The project uses Angular 6< and PHP 5<. It also uses the libraries BabylonJS for the 3D and LazerDB for the JSON database.
[BabylonJS](https://github.com/BabylonJS/Babylon.js/tree/master/dist)
[LazerDB](https://github.com/Greg0/Lazer-Database)

## Installation
**1/ Drag and drop the contents of _/ready2use/_ at the root of your server.**
If you want to add AnonIB 3D to a subfolder, you will need to recompile the Angular project using this build command:
```bash
ng build --prod --base-href=/path-to-subfolder/
```

Add this .htaccess, modify _path-to-sub-folder_, and place it at the root of your sub-folder.
```bash
    RewriteEngine on
    RewriteCond %{REQUEST_FILENAME} -s [OR]
    RewriteCond %{REQUEST_FILENAME} -l [OR]
    RewriteCond %{REQUEST_FILENAME} -d
    RewriteRule ^.*$ - [NC,L]
    RewriteRule ^(srv|user)($|/) - [L]
    RewriteRule ^(.*) /path-to-sub-folder/index.html [NC,L]
```
Don't forget to add the content of _/src_php/_ in _/path-to-sub-folder/srv/_


**2/ Add you own custom map list**
Go to _/php/MapController.php_ and add and suppress a new line. Use only characters allowed in Url for the board name.
```bash
array_push($levelToPlace, new Level("newmap", 15, 13, true, true) );
```

**3/Initialize the admin password + the DB**
Go to _/srv/php/admin.php_
Type your password in the field
Click on Set password
To re-init the password go to  _/php/password/password.txt_ and erase the file
After this erase database + posts and maps if they already exist and click Init the database + Init Map and Posts

**4/Access to the admin**
Go to _/admin_ , type your password and click on New user or Existing user.
You know have access to the admin. Click on the Launch the Admin.
Posts is to review , delete or ban user.
Map is to change map. At the top you got a selector to choose the chan of the map, and at the bottom you got a selector for the type of tile you want to use.

## Project status
Alex paused the project due to his personal situation, this fork aims at making progress on his absence.

## Support
For any question or problem contact me by mail (pvnfu@hopto.org).
I don't yet know how everything works so I might redirect you to Alex at (monsieur.krunch@gmail.com) or on Twitter (https://twitter.com/alexkrunch)


## License
[MIT](https://choosealicense.com/licenses/mit/)
