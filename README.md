# Codeigniter-Blade-Theme-Engine
This library integrates Laravel's Blad Engine into Codeigniter with a theming functionality so you are not only limited to displaying views in the traditional CI style but it gives you the power to have as many themes as you want in one CI installation and you can switch themes anytime and anywhere you want.

### Installation
1. Clone/Download this repository.
2. Copy all files to your CodeIgniter folder.
3. Open ```application/config/autoload.php```
4. Add ```theme``` to the following arrays 
	``` php 
	$autoload['libraries'] = array('theme');
	```
	```php
	$autoload['helper'] = array('theme','url');
	```
	```php
	$autoload['config'] = array('theme');
	```
	
#### Install Blade Package
We are using [duncan3dc/blade](https://github.com/duncan3dc/blade) which is a standalone package of Blade.
So Install the said package via Composer by issuing this command
```bash
composer require duncan3dc/blade
```

Make sure you have Configured Using Composer with your CodeIgniter in ```config.php``` file

### Configuration
1. Create a Directory ```themes``` in your CodeIgniter's root directory
2. You are free to Change the name of ```themes``` directory
3. Create ```default``` directory in the ```themes``` directory
4. Open ```application/config/theme.php```
5. You can see some Configuration items.
6. If you have changed the name of ```themes``` directory, configure that in 
	```php
	$config['theme_directory'] = FCPATH.'themes'.DIRECTORY_SEPARATOR;
	```
7. If you have changed the sub directory of themes from ```default``` to something else, Configure that in
	```php
	$config['theme_default'] = 'default';
	```
	
### Usage
In the ```application/config/theme.php``` file, You have configured the default theme name.
Which will be used as your default directory where the library will look for views/template files.

Go to ```themes/default``` directory and create ```welcome.blade.php``` file.

Paste the following Text in that file.
```html
<DOCTYPE html>
<html lang="en">
<head>
	<title>{{$page_title}} - CodeIgniter</title>	
</head>
<body>
<h1>Welcome {{$person}}!</h1>
</body>
</html>
```
Now in your controller, do the following
```php
<?php
defined('BASEPATH') OR exit('No direct script access allowed');

class Welcome extends CI_Controller {

	public function index()
	{
	    $view_data = array(
	        	'page_title' => 'Blade template Engine came to CodeIgniter',
			'person_name' => 'Fayaz Khan'
        	);
		$this->theme->display('welcome',$view_data);
	}
}

```


That's it, Navigate to ```/welcome``` and you will see the Blade template engine working the way you want,

### Documentation
You can find usage and all documentation of Blade Template engine @ [Laravel Official Website](https://laravel.com/docs/5.3/blade)

### Contribution, Feedback and suggestions
This is the initial version of blade theming engine. I am looking forward to see your feedback and suggestions. I will be adding more features to this library as I get free time.

Happy Coding
