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

after this, Look below in the `config.php` file until you find 

`$autoload['helper'] = array();`

like above, type `theme` in the helper's `array()` like 

`$autoload['helper'] = array('theme');`

A little below of that line in `config.php` file, you should find 

`$autoload['config'] = array();`

We have to put `'theme'` in the array of configs too so your line should look like

`$autoload['config'] = array('theme');`

_Note:_ we are using [duncan3dc/blade](https://github.com/duncan3dc/blade) which is a standalone package of Blade.

If you are using `Composer` with Codeigniter the you have to just run the following command from composer within your codeigniter's directory

`composer require duncan3dc/blade`

If you are not using Composer, Download that package and put it in your Codeigniter's root directory whereever you like, Just remember the path and of course, Run `composer install` so that the package dependencies become available to the Blade package

Now, from the CodeIgniter's directory, Open `application/config/theme.php`

You should see the following line

`$config['blade_engine'] = FCPATH.'vendor/blade/vendor/autoload.php';`

If you are using Composer and installed the Blade package via composer, you should leave it empty or as is. Otherwise, please put the Path to the autoloader of the blade package.

_Tip:_ Create a directory `vendor` in your Codeigniter's root and put the downloaded duncan3dc/blade package in that directory with name `blade`, RUn `composer install` from that directory and you are ready to go with that default path.

After installing and configuring everything, Its time to create out theme directory structure and setup our theme

