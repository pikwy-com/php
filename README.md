Pikwy - Online Solution to create Screenshot

function SiteScreenshot($token, $url, $width, $height, $response_type = 'image') {
	// Parameters.
	$token = $token; ///YOUR_API_TOKEN
	$url = urlencode($url);
	$width = $width;
	$height = $height;
	$response_type = $response_type; ///Response type: json, image

	// Create the query URL.
	$query = "https://api.pikwy.com/";
	$query .= "?token=$token&url=$url&width=$width&height=$height&response_type=$response_type";

	// Call the API.
	$image = file_get_contents($query);

	// Store the screenshot image.
	file_put_contents('./screenshot.png', $image);
}
