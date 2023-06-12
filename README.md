# php_practice
QUESTION 1:
index.html
<!DOCTYPE html>
<html>
<head>
    <title>File Upload</title>
</head>
<body>
    <form action="upload.php" method="POST" enctype="multipart/form-data">
        <label for="file">Select a file:</label>
        <input type="file" name="file" id="file">
        <input type="submit" value="Upload File">
    </form>
</body>
</html>


upload.php:

<?php
$target_dir = "C:/xampp/htdocs/cwharry/";
$target_file = $target_dir . basename($_FILES["file"]["name"]);

// if everything is ok, try to upload file
{
  if (move_uploaded_file($_FILES["file"]["tmp_name"], $target_file)) {
    echo "The file "." has been uploaded.";
  } else {
    echo "Sorry, there was an error uploading your file.";
  }
}
?>



QUESTION 2:

function addCommasToInteger(number) {
  // Convert the number to a string
  var numberString = number.toString();

  // Split the string into an array of characters
  var chars = numberString.split('');

  // Initialize variables
  var result = '';
  var count = 0;

  // Iterate through the characters in reverse order
  for (var i = chars.length - 1; i >= 0; i--) {
    // Add the current character to the result
    result = chars[i] + result;

    // Increment the count
    count++;

    // Add a comma after every third character
    if (count % 3 === 0 && i !== 0) {
      result = ',' + result;
    }
  }

  // Return the result
  return result;
}

// Example usage
var number = 1234567;
var formattedNumber = addCommasToInteger(number);
console.log(formattedNumber); // Output: "1,234,567"
