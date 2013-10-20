# dubotics.github.io

## Overview

This layout of this website is built on top of Twitter-Bootstrap, and is served using Jekyll.

## Build Instructions

1. Install Ruby (version 1.9.3 or 2.0.0)
2. Install Bundler: `gem install bundler`
3. Install dependencies: `bundle install`
4. If you are running Windows, you MUST do the following due to a bug in the syntax highlighter
    plugin used:
    
        gem uninstall pygments.rb --version "=0.5.2"
        gem install pygments.rb --version "=0.5.0"

## Testing the website

1. Build and serve the site: `jekyll serve --watch`. 
    1. This will automatically rebuild the website whenever any changes are made.
    2. If you modify `_config.yml`, then you must restart the entire command.
3. Navigate to `localhost:4000` in your web browser to locally view the website

## Deploy

To deploy, simply push all changes to the master branch on Github:

    git add -A
    git commit -m "Add commit message here"
    git push origin master
    
The website at `http://dubotics.github.io` will automatically update. This usually happens
instantaneously, but can take up to 10 minutes, if Github is being slower then usual.

Note: your web browser may cache the website, and continue displaying the old version.
To force it to reset, try holding shift and pressing the "refresh" button to force it 
to clear the cache.

## Configuration

All the configuration options can be found in `_config.yml`.  