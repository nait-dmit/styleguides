# Using Sass [Windows]

## Install

### Step 1: Install Ruby

1. Download Ruby Installer for Windows: http://www.rubyinstaller.org/

1. install the recommended ruby version (currently "Ruby 1.9.3-p545” at the time of this writing) from the downloads page.

1. Leave all of the installer settings as default __except check the “Add to PATH” option__, which is necessary so that the ruby and gem binaries, as well as any executables installed via rubygems, can be run from any directory on the command line.

1. Restart your computer so that the changes can take effect.

1. Verify from the cmd prompt by running `ruby -v`, should report the version number.

### Step 2: Install Sass

1. From the cmd prompt run: `gem install sass`

1. Verify from the command prompt with `sass -v`, should report the version number.

### Step 3: There is no step 3.

That's it.



## Use

### Step 1: CD To Project Directory

On the command line, move to your working directory for the project you want to use Sass with. `cd C:\path\to\project`

### Step 2: Run the Watcher

1. use `sass --watch` from the command line to have Sass watch for changes to your .sass or .scss files. Run `sass --help` to see various options. A few of my favourites are `--line-numbers` `--style compact`


__Syntax:__ `sass --option-1 --option-2 --watch input\path\:output\path\`

__Example:__ `sass --line-numbers --style compact --watch .:.`

_I know this looks odd, but it's simply watching the current directory for input, and outputting to the same (current) directory_

### Step 3: Work!

Go ahead and (continue to) work on your project. Any `.sass` or `.scss` files will be converted to `.css` files on-the-fly.

_Note: any files which begin with an underscore will not be converted, but will still be available for_ `@import`, _use this method to break up your monolithic CSS file into a number of discrete Sass files._

__Example:__

* project/directory/
  * index.html
  * stylesheets/
    * style.css (will be generated for you)
    * style.sass (imports _normalize.sass and _typography.sass )
    * _normalize.sass
    * _typography.sass
