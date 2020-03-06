# MPA front-end-architecture

## terms
### page
The view returned given a URL
### app shell
The consistent views and wrapping elements between pages
### content
The page specific elements of a give URL

**Thesis: Each `page` in a `MPA` is an `application`**

## Housing Structure

![alt text](https://github.com/tamb/front-end-architecture/blob/master/MPA%20-%20Level%200.jpg)


### Shared Application Dependencies
These can be organizes into directories for SCSS, JS, Fragments... anything we homebrew that is used across apps/pages

### App
This is a directory that should be name of the URI (if we are visiting `/users.html` the directory/app name should be `users`.

## App Structure

![](https://github.com/tamb/front-end-architecture/blob/master/MPA%20-%20Level%201.jpg)

### Component Directories
 You should have 1 Component Directory per component.  If the component is named `UserProfile` the directory should be named `UserProfile`. 

### Utility Directories
This represents various directories for certain services or utilities the application needs.
If you have a `store` for state management you should create a `store` directory and house all relevant files within that directory.  

### app.html
This is the `.html` file that the url will render.  Consider this the home document for this app.

### app.js
This is the entry level JavaScript file that webpack will begin gather dependencies from.  It will output as many files as directed.  This file should import page-level JS dependencies (dependencies that are not component-specific).  This file should also import `app.scss` for processing via webpack.

### app.scss
This is the root level SCSS file that should import page-level CSS dependencies (those are dependencies that are not component-specific)

## Component Directory Structure

![](https://github.com/tamb/front-end-architecture/blob/master/MPA%20-%20Level%202.jpg)

### Component.html
This file should contain only component-specific `.css` and `.js` files.  The file name should match the component name.  So `UserProfile` should yield `UserProfile.html`. 

### Component.js
This file should contain only component-specific `.js` files and programs.  The file name should match the component name.  So `UserProfile` should yield `UserProfile.js`. This file shoul import the component's `.scss` file for processing.

### Component.scss
This file should contain only component-specific `.scss` files and styles.  The file name should match the component name.  So `UserProfile` should yield `UserProfile.scss`. 

### Utilities
Utilities within the component directory should be sparse.  They represent JS that is easier to comprehend when placed in its own module.

## Root Files Structure
