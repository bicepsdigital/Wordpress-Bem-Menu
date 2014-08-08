# Wordpress BEM Menu

Say goodbye to badly named menus in Wordpress and say hello to Wordpress BEM Menus!

To use simply drop the contents of wp_bem_menu.php into your functions.php file.


## Usage

First you need to create a menu in wp-admin and make sure it is assigned a theme location. Then insert the following function into your theme. The first argument is the theme location (as defined in wp-admin) and the second argument is the class prefix you would like to use for this particular menu.

```php
<?php bem_menu('menu_location', 'my-menu'); ?>
```

## Css classes

The syntax is very simple, all menu items are logically grouped by depth to avoid some of the nesting issues of the standard output.

```css
/* Top level items */
.my-menu__item{}

/* Specific link (where x = post_id) */
.my-menu__item--x{}

/* Parent item */
.my-menu__item--parent{}

/* Active page item */
.my-menu__item--active{}

/* Parent of the current active page */
.my-menu__item--parent--active{}

/* Ancestor of the current active page */
.my-menu__item--ancestor--active{}

/* sub menu class */
.my-menu__sub-menu{}

/* sub menu item */
.my-menu__sub-menu__item{}

/* Specific sub menu (where x is the menu depth) */
.my-menu__sub-menu--x{}

```

## Modification

BEM syntax is very subjective and different developers use different conventions. If you wish to change or adapt the syntax to go with your own implemntation all the menu suffixes are contained within the `$this->item_css_classes` array:

```php
$this->item_css_classes = array(
    'item'                      => $this->css_class_prefix . '__item',
    'parent_item'               => $this->css_class_prefix . '__item--parent',
    'active_item'               => $this->css_class_prefix . '__item--active',
    'parent_of_active_item'     => $this->css_class_prefix . '__item--parent--active',
    'ancestor_of_active_item'   => $this->css_class_prefix . '__item--ancestor--active',
    'sub_menu'                  => $this->css_class_prefix . '__sub-menu',
    'sub_menu_item'             => $this->css_class_prefix . '__sub-menu__item',
);

```




