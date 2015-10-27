# Moodle Clean Child Theme

A **basic** boilerplate child theme, inherits [Moodle's "Clean"](https://docs.moodle.org/29/en/Standard_themes) standard theme.

Beta! Work in progress...

 * Clean Theme: https://docs.moodle.org/dev/Clean_theme

## Requirements

 * Moodle >= 2.5
 * clean theme >= 2015100100

## Theme Dev

 * https://docs.moodle.org/dev/Themes_overview
 * https://docs.moodle.org/dev/Page_API

### Related Moodle Api's

 * https://docs.moodle.org/dev/Output_API
 * https://docs.moodle.org/dev/Navigation_API

## Clean theme

 * https://docs.moodle.org/dev/Clean_theme

## Basic install this theme
This basic walkthrough aims to users with some php experience which are new to Moodle.

First you have to decide on a short name for your new Moodle Theme., i.e. `mytheme`

### 1. Basics

 * clone or download this repository in to the Moodle theme folder `/<root_moodle/docs_moodle/theme`
 * Rename the newly created folder to your shortname (i.e. `/<root_moodle/docs_moodle/theme/mytheme`)

### 2. Config file

Some neccessary adjustments in the  the `config.php`:

 * set `$THEME->name` to your sexact short name (i.e `$THEME->name = 'mytheme';`)
 * `$THEME->sheets = array('custom','cleanchild')`.
 $THEME->sheets defines the stylesheets loaded by your theme. The second entry refers to an empty css file `style/cleanchiild.css'` wich you can use for your custom styles.  Alternatively rename bots the css file and the array entry. Add any stylesheet you want by locating them into the `style` folder and appending them to the array. (rule: filename without extension)
 Leave the `clean` entry as the first element in this array to ensure a proper queuing of the loaded css files.

The  `config.php` offers a lot more options. See the Moddle docs for this: https://docs.moodle.org/dev/Theme_config_file

### 3. Version file

 @TODO

### 4. Edit Language File

  * browse to the `lang/en` folder. Rename the `theme_cleanchild.php` to `theme_<my-short-name>.php` (i.e.  `theme_mytheme.php`)
  * open the file and edit `$string['pluginname'] ` and `$string['choosereadme'] `. You can use markup in the latter.

### 5. Install via Moddle Site Administration

 @TODO

## Quick dev notes


Example include

```
<?php
// common header for layout files
require_once(dirname(__FILE__).'/inc/common-header.php');
?>
```

Example custom file, however you should rather use the `config.php` for loading scripts and styles

```
<link rel="stylesheet" href="<?php echo $CFG->wwwroot;?>/theme/cleanchild/my-extra.css" type="text/css" media="screen" />
```

Example logo

```
<img src="<?php echo $OUTPUT->pix_url('logo', 'theme'); ?>" />
```

Is frontpage *or* login page:

```
<?php
if ($PAGE->pagelayout == 'frontpage' || $PAGE->pagelayout == 'login') {
    return true;
}
?>
```

Add custom body class (layout file name)

```
<body <?php echo $OUTPUT->body_attributes(array('layout-'.basename(__FILE__, '.php'))); ?>>
```

## License

* [GNU GPL v3 or later](http://www.gnu.org/copyleft/gpl.html), inherited from Clean/Moodle
