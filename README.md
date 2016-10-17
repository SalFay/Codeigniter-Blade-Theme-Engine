# Codeigniter-Blade-Theme-Engine
This library integrates Laravel's Blad Engine into Codeigniter with a theming functionality so you are not only limited to displaying views in the traditional CI style but it gives you the power to have as many themes as you want in one CI installation and you can switch themes anytime and anywhere you want.

## Installation
First off, Grab [Clone/Download](https://github.com/SalFay/Codeigniter-Blade-Theme-Engine/archive/master.zip) a fresh copy of this library and unzip it.
You will get a directory structure similar to this

- application
    - libraries
        - Theme.php
    - config
        - theme.php
    - helpers
        - theme_helper.php

You must have CodeIgniter, Now just copy and paste the files into the CodeIgnitor's Directoy like below.

- From Downloaded Package
    - application/libraries/Theme.php
- to CodeIgniter
    - application/libraries/Theme.php

- From Downloaded Package
    - application/config/theme.php
- to Codeigniter
    - application/config/theme.php
    
- From Downloaded Package
    - application/helpers/theme_helper.php
- to CodeIgniter
    - application/helpers/theme.php
    

Now, That you have copied all files to the appropriate directories in CodeIgniter Framework, Its time for a little coding

From Codeigniter's directory, Open `application/config.autoload.php` and locate a line like below one

`$autoload['libraries'] = array();`

Type `theme` in the `array()` so your could should look like 

`$autoload['libraries'] = array('theme');`


