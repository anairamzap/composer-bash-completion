#### Bash completion for Composer Drupal packages
This repository was forked from https://github.com/iArren/composer-bash-completion, 
I've just did a cheap replacement in the grep filtering, to restrict packages to drupal modules.


##### Requirements

* composer
* drupal
* bash :p

##### Installation

1. Get the bash completion script and move it to `/etc/bash_completion.d/composer`:

    ```
    wget https://raw.githubusercontent.com/anairamzap/composer-bash-completion/master/composer && mv composer /etc/bash_completion.d/composer
    ```

    Note, that you would probably need root privileges to mv the file. If that's the case just add 'sudo' before mv command `sudo mv composer /etc/bash_completion.d/composer`
2. Create a symlink to `/usr/share/bash-completion/completions`:

    ```
    ln -s /etc/bash_completion.d/composer /usr/share/bash-completion/completions/composer
    ```

    Once again, add root privileges with sudo if needed.


3. Source your bahsrc to 'apply changes' or restart your console:

    ``` source ~/.bashrc
    ```

##### Usage

Before using completion you should install a composer as `composer` executable.
After then all done you can use it like you use `apt-get` with auto-completion.
Here are some features:

* package name will be searched when using `require` command. 
So, for example you could type: `composer require drupal/men[TAB]` and bash should display all packages matching that pattern.

* packages names are restricted to drupal modules (this is done by a quick and dirty filtering by 'drupal/' using grep)
