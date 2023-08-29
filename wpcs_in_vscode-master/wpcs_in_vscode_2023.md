# How to set up WordPress Coding Standards in Visual Studio Code.

> Before you start, can check this out - https://github.com/WordPress-Coding-Standards/WordPress-Coding-Standards

1. Install Cmder(with Git for Windows)
2. Install Composer
    - While installing composer select 'Developer Mode'
    - Escape proxy setting, click Next.
3. Write the command in Cmder (Recommend 'Git') = `composer global require squizlabs/php_codesniffer`
4. After installing Codesniffer write this command in the location = C:\composer> `composer require wp-coding-standards/wpcs`
5. Cloning a Git repository at the location C:\composer> vendor> `git clone https://github.com/PHPCompatibility/PHPCompatibility.git`
6. Link up WPCS with PHPCompatibilly Standards with PHPCS :
`phpcs --config-set installed_paths C:/composer/vendor/PHPCompatibility,C:/composer/vendor/wp-coding-standards/wpcs`
7. Check if the WordPress in listed by the command `phpcs -i`
8. Now For “Visual Studio Code” go to
File > Preferences > Settings > Extensions > PHP Codesniffer > Standard > Add php path and standard like below 👇
    ```
    {
    "php.validate.executablePath": "C:\\xampp\\php\\php.exe",
    "php.executablePath": "C:\\xampp\\php\\php.exe",
    "phpcs.enable": true,
    "phpcs.executablePath": "C:\\Users\\Forhad\\AppData\\Roaming\\Composer\\vendor\\bin\\phpcs.bat",
    "phpcs.standard": "WordPress",
    }
    ```
    > Make sure path is correct by command `where php`, `where phpcs` & `where phpcbf`
8. Now going to add PHP to Windows Path Variable 
    - Search Start menu > "Advanced system settings"
    - Click "Environment Variables…"
    - System variables > path > Edit > New
    - Xampp users php path C:\xampp\php\php.exe
    - After adding path in system variable, restart the windows will be required!

## Automatically formated by PHPCBF

- Got to vscode extensions and search "phpcbf" by "Per Soderlind"
- install it
- go to preferences > settings > edit in settings.json
- and paste below code
    
    ```
    "phpcbf.enable": true,
    "phpcbf.onsave": false,
    "phpcbf.debug": true,
    "phpcbf.standard": "WordPress",
    "phpcbf.executablePath": "C:\/Users\/Forhad\/AppData\/Roaming\/Composer\/vendor\/bin\/phpcbf.bat",
    ```
    > Make sure the path 'phpcbd.bat' is currect. To know command `where phpcbf`
    
Now go to any WordPress file and 'right click' to select Formate Document or press Ctrl+Alt+F
