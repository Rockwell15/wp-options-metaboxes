# wp-options-metaboxes

wp-options-metaboxes is a lightweight class to add metabox layouts to any WordPress page

![](https://raw.githubusercontent.com/Rockwell15/wp-options-metaboxes/master/backend-screenshot.png "Example picture")

## Example Usage:

```

	// include the file
	include('wp-options-metaboxes.class.php');

	// create the class
	$metaboxes = new Options_Metaboxes();

	// add settings metaboxex
	foreach ( $this->meta_boxes as $settings_section => $meta_box ) {
		$metaboxes->add_settings_metabox( $settings_section, $meta_box['title'], false );
	}

	// get the HTML from a settigns field, then add as a sidebar metabox
	$settings_fields = $metaboxes->get_settings_html('settings-section');
	$metaboxes->add_settings_metabox( $section, $meta_box['title'], false );

	// adds a publish style metabox
	$publish_title  = __( 'Save Settings', 'linkedin-company-updates' );
	$inside_metabox = 'Some info or whatever you wanna put up in here';
	$metaboxes->add_publish_metabox( $publish_title, $inside_metabox );

	// output the HTML
	$metaboxes->output();

```