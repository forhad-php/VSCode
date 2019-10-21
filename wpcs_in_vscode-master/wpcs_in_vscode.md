# How to set up WordPress Coding Standards in Visual Studio Code.

> Before you start, can check this out - https://github.com/WordPress-Coding-Standards/WordPress-Coding-Standards

1. Install Composer
    - While intalling composer select 'Develper Mode'
    - Escape proxy setting, click Next.
2. Write this command in cmd (Recommend 'Git Bash')
    - C:\composer> composer global require squizlabs/php_codesniffer 3.4.1
    - (go to - packagist.org/explore/ and search by name of package and see version number)
3. After install codesniffer then write this command in cmd
    - C:\composer> composer require wp-coding-standards/wpcs 2.0.0 (also check the version)
4. Now make sure have installed git
    - C:\composer> vendor>git clone https://github.com/wimg/PHPCompatibility.git
5. Link wpcs and PHPCompatibilly Standards with phpcs :
    - phpcs --config-set installed_paths C:/composer/vendor/PHPCompatibility,C:/composer/vendor/wp-coding-standards/wpcs
    - NOTE : phpcs maybe found in C:\composer\vendor\squizlabs\php_codesniffer
        - Hold the file and release in git bash for geting actual path.
6. Check installed coding standerd list by the command.
    - phpcs -i
    - Can found 'wordpress' in the list? Maybe not.
7. Now For “Visual Studio Code” go to
    - File > Preferences > Settings > Extensions > PHP Codesniffer > Standard > Add php path and standard like below
    ```
    {
    "php.validate.executablePath": "C:\\xampp\\php\\php.exe",
    "php.executablePath": "C:\\xampp\\php\\php.exe",
    "phpcs.standard": "WordPress",
    }
    ```
    > Make sure path is correct by command `where php`, `where phpcs` & `where phpcbf`
8. Now going to add PHP to Windows Path Variable 
    - Search Start menu > "Advanced system settings"
    - Click "Environment Variables…"
    - User variables > path > Edit..
    - At the end of the path write a semicolon sign ";" and then paste php.exe path
    - Xampp users php path C:\xampp\php\php.exe

## Automatically formated by PHPCBF

- Got to vscode extensions and search "phpcbf" by "Per Soderlind"
- install it
- go to preferences > settings > edit in settings.json
- and paste below code
    
    ```
    "phpcbf.onsave": true,
    "phpcbf.debug": true,
    "phpcbf.standard": "WordPress",
    "phpcbf.executablePath": "C:\/Users\/Forhad\/AppData\/Roaming\/Composer\/vendor\/bin\/phpcbf.bat",
    ```
    > Make sure the 'phpcbd.bat' is currect.
    
Now go to any WordPress file and 'right click' to select Formate Document or press Ctrl+Alt+L
