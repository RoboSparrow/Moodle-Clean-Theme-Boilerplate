# Moodle Clean Child Theme

A quick and **basic** boilerplate theme. For Moodle noobs like me.

Work in progress...

 * Clean Theme: https://docs.moodle.org/dev/Clean_theme

## Requirements

 * Moodle >= 2.5

## Theme Dev

 * https://docs.moodle.org/dev/Themes_overview
 * https://docs.moodle.org/dev/Page_API

### Related Moodle Api's

 * https://docs.moodle.org/dev/Output_API
 * https://docs.moodle.org/dev/Navigation_API

## Clean theme

 * https://docs.moodle.org/dev/Clean_theme

## Renaming this theme

 @TODO

## Quick dev notes


Example include

```
<?php
// common header for layout files
require_once(dirname(__FILE__).'/inc/common-header.php');
?>
```

Example custom file, however you should rather use the c=`config.php` for loading scripts and styles

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

## License

* [GNU GPL v3 or later](http://www.gnu.org/copyleft/gpl.html)
