# lib-menu

## Usage

To "install" this library you need to update your build.gradle file in root. Add the new dependency (after other dependencies) and make sure the Enonic repository URL is set up for maven.

**Note:** The "gradle watch" command won't detect this change, so use "gradle deploy" after changing your build.gradle file.

### Gradle build script

```
repositories {
    maven {
        url 'http://repo.enonic.net/public'
    }
}

dependencies {
    include 'com.enonic.lib:menu:1.1.1'
}
```

### Controllers

In every controller you want to use it (Page, Part or Layout) you just add this at the top of the file:

```javascript
var menu = require('/lib/enonic/menu');
```

To access any of the functions from this library, just type something like this:

```javascript
var menuItems = menu.getMenuTree(2); // Get 2 levels of menu
```

### Mixin

Any content type that may appear in the menu will need a mixin named "menu-item" with a Checkbox field named "menuItem" and a TextLine
field named "menuName". This mixin **must** be added as x-data.

```xml
<!-- Add this line after the end of the config node -->
<x-data mixin="menu-item" />
```

Check the `_examples` folder for a few mixins you can just copy and paste into your site. Also read the readme-files in those folders for more information.

### Thymeleaf

We've included a bunch of examples of ready-to-go Thymeleaf code in the `_examples` folder, have a look there for a quick start. Also read the readme-files in those folders for more information.

## Compatibility

| Lib version        | XP version |
| ------------- | ------------- |
| 1.0.0 | 6.0.0 |
| 1.1.0 | 6.1.0 |
| 1.1.1 | 6.1.0 |
| 1.2.0 | 6.3.0 |
