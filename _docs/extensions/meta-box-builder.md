---
title: Meta Box Builder
---

## Overview

Meta Box Builder is the most popular extension for Meta Box users and is the mandatory tool for almost everyone.

This extension creates an UI for you to add and manage your custom fields. So you don't need to [touch code again](https://docs.metabox.io/creating-meta-boxes/). It's helpful for both beginners (who have little knowlege about PHP coding) or experience developers (who want to save time). You can also use it to create [settings pages](https://metabox.io/plugins/mb-settings-page/) or [relationships](https://metabox.io/plugins/mb-relationships/).

If you already used our free [Online Generator](https://metabox.io/online-generator/), then this extension works similarly. But it has a better support (very much) for all field types and other extensions and it works right in the WordPress admin area.

Take a look at the screenshot:

![meta box builder ui](https://i.imgur.com/DQBeWJN.png)

For more information, please see the [extension page](https://metabox.io/plugins/meta-box-builder/).

This guide cover basic tasks a user may carry out when using our builder.

{% include installation.html %}

After installing, the plugin creates a sub-menu **Custom Fields** under the top-level menu **Meta Box** in the WordPress admin.

![meta box builder menu](https://i.imgur.com/EHd1v23.png)

Clicking on that menu will bring you to the screen where you can create meta boxes and custom fields.

Please note that the screen says **Field Groups** instead of **Meta Boxes**. We think the term "meta box" might be confusing, since it's the name of the [Meta Box plugin](https://metabox.io). Besides, the meta box builder is for creating custom fields, using field group with a simple meaning of "set of custom fields" makes sense. This term also works in case you want to build [front-end forms](https://metabox.io/plugins/mb-frontend-submission/), [settings pages](https://metabox.io/plugins/mb-settings-page/) or [user fields](https://metabox.io/plugins/mb-user-meta/).

## Creating a field group

To create a field group, go to *Meta Box &rarr; Custom Fields*. Then click the **Add New** button.

![creating a meta box (field group)](https://i.imgur.com/atmAw8E.png)

On the add new field group screen, enter the field group title in the **Title** box. The field group ID is then automatically generated. You can change the ID if you want, it's optional.

Then select the fields you want to add to the field group by clicking the **+ Add Field** button. When click on a field, it will be automatically added to the list of fields in the field group. We'll see the settings of each fields in a section below.

{% include alert.html content="To find a field type quickly, type its name in the input box above the field list. The plugin will filter the fields and show only matched fields." %}

While working on fields, you can:

- Delete or duplicate a field by clicking the icons in the field title bar.
- Reveal field settings by clicking anywhere in the field title bar.
- Reorder fields by drag and drop fields to the new positions.

When it's done, click button **Publish** to save the field group. You also can click on **Save as Draft** link if you don't want to publish it, e.g. making it not available in the edit post screen.

## Field settings

When adding fields to a field group, each field has its own settings. The list of settings with detailed explaination is [here](https://docs.metabox.io/field-settings/). Meta Box Builder simply creates UI for them.

To view and edit field settings, click anywhere in the field title bar:

![Edit field settings](blob:https://imgur.com/3a89bb1e-59de-9349-bba2-aabf89bfa0f7)

Each field settings are self-explained. We also add some tooltips next to the setting title to give you more information if needed.

All field settings are divided into 2 tabs: General, Advanced. The General tab has most settings you need. The Advanced tab has the following settings:

- Before & after: For entering custom HTML that outputed before and after the field.
- Custom CSS class: if you need to cusomize the style of the field.
- Custom sanitize callback: if you need [custom sanitization](https://docs.metabox.io/sanitization/).
- Save field value: if you don't want Meta Box to save the field value (which rarely happens) and you want to handle saving by yourself, then uncheck this checkbox.
- Custom HTML5 attributes: helps you add [custom HTMl5 attributes](https://docs.metabox.io/custom-attributes/) to your input fields.
- Validation: helps you to create [complex validation rules](https://docs.metabox.io/validation/).
- Custom settings: if you want to add extra settings to the field. We'll cover it in a next section.
- Conditional logic: if you install the [Meta Box Conditional Logic](https://metabox.io/plugins/meta-box-conditional-logic/), then this part is for creating rules with UI.

![edit field advanced settings](https://i.imgur.com/jKU2B56.png)

Note that: plugins and developers might add more settings for fields. We'll see how to do that later in this docs.

## Field group settings

The field group settings are put in the tab **Settings**:

![field group settings](https://i.imgur.com/K3emckr.png)

There are several settings:

- Location: where you select this field group is for posts, terms, users, comments, blocks or settings pages. For each object type, you'll be able to select corresponding post types, taxonomies or settings pages. Please note that it's required to install and activate corresponding extensions: [MB Term Meta](https://metabox.io/plugins/mb-term-meta/), [MB User Meta](https://metabox.io/plugins/mb-term-meta/), [MB Comment Meta](https://metabox.io/plugins/mb-comment-meta/), [MB Blocks](https://metabox.io/plugins/mb-blocks/), and [MB Settings Page](https://metabox.io/plugins/mb-settings-page/).
- Advanced location rules: allows you to add advanced rules for which category, post, user, ... the field group appears for. Requires the [Meta Box Include Exclude](https://metabox.io/plugins/meta-box-include-exclude/) extension.
- Toggle rules: select which conditions to show or hide the field group. Requires the [Meta Box Show Hide](https://metabox.io/plugins/meta-box-show-hide/) extension.
- Conditional Logic: setup the conditional logic rules to toggle the field group based on other fields' values. Requires the [Meta Box Conditional Logic](https://metabox.io/plugins/meta-box-conditional-logic/) extension.
- Post settings, such as context, priority if you select the location is for posts.
- Custom block settings, such as block icon, render callback if you select the location is for blocks, which means creating custom Gutenberg blocks. Requires [MB Blocks](https://metabox.io/plugins/mb-blocks/) extension. See the **Create Gutenberg blocks** section below.
- Tab style and default active tab: these are the settings for [Meta Box Tabs](https://metabox.io/plugins/meta-box-tabs/) extension.
- Custom table settings, including table name, table prefix and option to create custom table automatically. These are the settings for [MB Custom Table](https://metabox.io/plugins/mb-custom-table/) extension. Note that if you select to create the custom table automatically, all columns will have the data type `TEXT` to ensure maximum compatibility.
- Custom CSS class: the custom CSS class for the wrapper `div` if you need to cusomize the style of the field group.
- Field ID prefix: if you want to prefix all fields in the field group, then this settings is for that. It's optional, but a good practice to keep your custom fields separated from other custom fields. You can also use underscore `_` as prefix to keep your fields hidden in the default WordPress **Custom Fields** meta box.
- Custom settings: if you want to add extra settings to the field group. See below for details.

## Custom settings

Custom settings is a feature for both fields and field groups, which allows you to add extra settings for them in case the builder doesn't have. It's useful when you want to add your own settings or the settings the builder hasn't added yet (in this case, please let us know).

{% include alert.html content="What describes in this section is applied also for similar settings like Query args and Custom HTML5 attributes." %}

To add custom settings, click on Advanced tab for fields or go to Settings tab for the field group. Then click **+ Add New** button and add new settings. For example, if you want to create a text field that has 2 extra settings:

```php
[
    'id'   => 'new-your-phone',
    'name' => 'New Your phone',
    'type' => 'text',
    
    // Custom settings.
    'mask'   => '012-345-6789',
    'enable' => false
],
```

Then enter as follows:

![custom settings](https://i.imgur.com/WFRBdL4.png)

Remember, Meta Box Builder treats `true`, `false` as boolean values.

If the field requires complex settings, like multi-dimentional arrays:

```php
[
    'type'       => 'post',
    'id'         => 'field_id',
    'query_args' => [
        'tax_query' => [
            [
                'taxonomy' => 'category',
                'field'    => 'slug',
                'terms'    => 'technology',
            ],
        ],
    ],
],
```

Then you can use the dot notation or JSON for custom attributes:

### Dot notation

The dot notation allows you to define the data structure with dots. For the `tax_query` above, you can define with dot notation like so:

![dot notation](https://i.imgur.com/MPC06Fd.png)

Please note that `taxonomy`, `field`, and `terms` are children of the first child of `tax_query`, not direct children of `tax_query`, we need to use index `0`.

### JSON notation

Another way to enter nested array in Meta Box Builder, you can use JSON notation. Encode the whole array of `tax_query` and paste to it value. Like so:

![json value](https://i.imgur.com/2eTlviV.png)

## Getting PHP code

For each field group, Meta Box Buider can create a PHP code that you can copy and paste into your theme's `functions.php` file (or your plugin file) and then *deactivate the Meta Box Builder extension*.

This is helpful if you want to:

- [Share field groups to other websites](https://metabox.io/copy-custom-fields-with-meta-box-builder/) which doesn't have Meta Box Builder installed.
- Improve the performance since field groups are loaded directly from your file.

To get the code, click the **Get PHP Code** button on the toolbar:

![export code](https://i.imgur.com/hcYgYWk.png)

On this screen, set the text domain (for field labels in case you want to translate them in a multilingual website) and the function name. Then click the **Generate** button to generate the code. Finally, click the **Copy** button to copy the code and paste it into your theme's `functions.php` file.

When you copy PHP code and paste it into your theme's `functions.php` file, you can **safely deactivate Meta Box Builder** (do *not* deactivate Meta Box, it's still required).

For detailed instruction, please see [this tutorial](https://metabox.io/copy-custom-fields-with-meta-box-builder/).

Please note that once you take the PHP code and remove the settings from the Meta Box Builder, there's no way to edit the field group in the Meta Box Builder directly from the exported code.

In order to do re-edit the field group, we suggest after taking the PHP code, export the field group settings from Meta Box Builder (see the section below). Then whenever you want to edit the field group, just import it back and edit.

## Export / Import

To export one or more field groups, go to the main screen *Meta Box &rarr; Custom Fields*. Then click the checkboxes next to the field groups' titles you want to export. Then choose **Export** from the Bulk Actions dropdown. Then click **Apply**.

![export field groups](https://i.imgur.com/r1moj0S.png)

Or you can export individual field group by clicking on **Export** link when hover the mouse over the field group title:

![export a single field group](https://i.imgur.com/Nx45cpH.png)

To import field groups, select the *Import* button at the top of the page. Then choose the downloaded file in the previous step, then press **Upload file and import**. That’s all!

![import field groups](https://i.imgur.com/UvGpqO5.png)

For detailed instruction, please see [this tutorial](https://metabox.io/export-import-custom-fields-meta-box-builder/).

Video tutorial:

<iframe width="560" height="315" src="https://www.youtube.com/embed/BGVY-5W6d7g?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## Creating Gutenberg blocks

Since v3.1.0, Meta Box Builder allows you to create Gutenberg blocks visually, without writing code. See this video tutorial on how to do that:

<iframe width="560" height="315" src="https://www.youtube.com/embed/v3ke1DBlWuk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Note that the plugin supports Twig template engine to write block template code. See [Twig documentation](https://twig.symfony.com/doc/1.x/templates.html) for how to use variables, conditions and functions.

For more convenient, the plugin supports the following variables:

- `{% raw  %}{{ align }}{% endraw  %}`: block alignment (if the block supports it).
- `{% raw  %}{{ anchor }}{% endraw  %}`: block anchor (if the block supports it).
- `{% raw  %}{{ className }}{% endraw  %}`: custom CSS class name (if the block supports it).
- `{% raw  %}{{ is_preview }}{% endraw  %}`: whether or not in preview mode.
- `{% raw  %}{{ post_id }}{% endraw  %}`: the current post ID.

To access the field value, you can use `{% raw  %}{{ field_id }}{% endraw  %}`, where `field_id` is the field ID. If the field returns an array (such as `single_image` field), you can access to field's attribute with `{% raw  %}{{ my_image.full_url }}{% endraw  %}`.

Besides, the plugin also allows you to use any PHP/WordPress function via `mb.function()` where `function` is the function name. For example, the code below get the post object and output the post title:

```php
{% raw  %}
{% set post = mb.get_post( post_id ) %}
{{ post.post_title }}
{% endraw  %}
```

Or this code will output the site title:

```php
{% raw  %}
{% set site_title = mb.get_bloginfo( 'name' ) %}
{{ site_title }}
{% endraw  %}
```

## Creating settings pages

This feature helps you to create custom settings pages (or Customize panels) with UI. It requires the [MB Settings Page](https://metabox.io/plugins/mb-settings-page/) extension.

To start, go to **Meta Box > Settings Pages** and click **Add New**.

![create settings pages](https://i.imgur.com/LXHfSkP.png)

Here you can enter all the settings for the settings page. All settings are self-explained. Please see the [documentation of MB Settings Page](https://docs.metabox.io/extensions/mb-settings-page/) to understand them.

## Creating relationships

This feature helps you to create relationships between posts, terms and users with UI. It requires the [MB Relationships](https://metabox.io/plugins/relationships/) extension.

To start, go to **Meta Box > Relationships** and click **Add New**.

![create relationships](https://i.imgur.com/XLP48tU.png)

Here you can enter all the settings for each side of the relationship (**From** and **To**). For each side, there are 3 tabs of settings:

- General: for general settings such as object type and post type.
- Meta Box: for extra meta box settings. These settings are the same as the field group settings when creating custom fields.
- Field: for extra field settings. These settings are the same as the field settings (post, term or user depending on the object type).

Please see the [documentation of MB Relationships](https://docs.metabox.io/extensions/mb-relationships/) to understand them.

## Adding your own field settings

If you develop [extra solutions for Meta Box](https://metabox.io/resources/), then you might need to add a custom settings for fields. Luckily, Meta Box Builder has API for you to create custom controls for these settings.

To add a control, use the following hook:

```php
add_filter( 'mbb_field_controls', 'your_prefix_add_field_controls', 10, 2 );

function your_prefix_add_field_controls( $controls, $type ) {
    // Add a checkbox control to the builder.

    $controls[] = \MBB\Control::Checkbox( 'custom_layout', __( 'Custom layout', 'your-text-domain' ) );

    // Add a select control to the builder.
    $controls[] = \MBB\Control::Select(
        'layout',
        [
            'label'   => __( 'Layout', 'your-text-domain' ),
            'tooltip' => __( 'Select the layout for the field', 'your-text-domain' ),
            'options' => [
                'one-third'  => __( 'One-third', 'your-text-domain' ),
                'one-half'   => __( 'One-half', 'your-text-domain' ),
                'two-third'  => __( 'Two-third', 'your-text-domain' ),
                'full-width' => __( 'Full-width', 'your-text-domain' ),
            ],
            'dependency' => 'custom_layout:true',
        ],
        'one-half',
        'general'
    );

    return $controls;
}
```

The filter `mbb_field_controls` accepts 2 parameters:

- `$controls`: Array of controls.
- `$type`: Field type, useful if you want to add controls to specific field types only.

Each control has a specific type (`\MBB\Control::Select` in the above example, which is a select dropdown) and several parameters:

1. Setting name
1. Control properties, which is an array:
    - `label`: the control label.
    - `tooltip`: the content of the tooltip, if you want to explain what the control is for users.
    - `options`: array of options for the select control, in format of `'value' => 'label'`.
    - `dependency`: if you want to show the control only when another control has a specific value, then set this to `{$other_control_setting_name}:{$value}`. Optional.
1. Default value. Optional.
1. Settings tab: `general` (default) or `advanced`. Optional.

In case your control has only `label` property, you can set the property as a string (see the checkbox control in the above example).

List of supported control types:

Name|Description
---|---
`\MBB\Control::Checkbox` | A checkbox
`\MBB\Control::Input` | An input text. You can set the `'type' => 'number'` for the control property to make it accepts only numbers.
`\MBB\Control::Select` | A select dropdown where you can select only a single value. You need to set `options` property for the control as shown in the above example.
`\MBB\Control::ReactSelect` | A select dropdown where you can select multiple values. You need to set `options` property for the control and the default value must be an array.
`\MBB\Control::Textarea` | A textarea.

This is the result of the above example:

![custom field controls](https://i.imgur.com/dk7Pcrf.png)

## Further reading

- [How to Add and Configure Custom Fields Using Meta Box Builder](https://metabox.io/add-configure-custom-fields-meta-box-builder/)
- [How to Export and Import Custom Fields with Meta Box Builder](https://metabox.io/export-import-custom-fields-meta-box-builder/)
- [How to Easily Copy Custom Fields From One Site to Others with Meta Box Builder](https://metabox.io/copy-custom-fields-with-meta-box-builder/)
- [Create Columns in Meta Box Builder](/create-columns-in-meta-box-builder/)
