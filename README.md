# Codeigniter Firebase Library

1. Install [kreait/firebase-php](https://firebase-php.readthedocs.io/en/stable/overview.html) package with Composer.
```
composer require kreait/firebase-php ^4.18
```

2. Edit file `application/config/autoload.php` replace this following line.
```
...
$autoload['libraries'] = array('firebase');
...
$autoload['config'] = array('firebase');
...
```

3. Goto [Firebase Console](https://console.firebase.google.com) navigate to Project settings -> Service accounts in the Firebase Admin SDK tab, click to the "Generate new private key" button then click "Generate key" to download .json file and save as to `application/config` folder in the project.

4. Copy your .json file name from step 3. replace it to `application/config/firebase.php` file in the `$config['filebase_app_key]` array like this.
```
$config['firebase_app_key'] = __DIR__ . '/../config/your-app-firebase-adminsdk-xxxxx-xxxxxxxxxx.json';
```

5. Now. You can use firebase library in the Controller file like this.
```
$this->load->library('firebase');
$firebase = $this->firebase->init();
$db = $firebase->getDatabase();
```

You can find more usage examples at https://firebase-php.readthedocs.io/en/stable/overview.html#usage-example.
and 
https://www.cloudways.com/blog/php-firebase-integration
