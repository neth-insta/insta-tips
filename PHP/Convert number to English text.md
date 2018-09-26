# Convert number to English text
```php
<?php

function num_to_text($number) {

    // zero is a special case, it cause problems even with typecasting if we don't deal with it here
    $max_size = pow(10, 18);
    if (!$number)
        return "zero";
    if (is_int($number) && $number < abs($max_size)) {
        switch ($number) {
            // set up some rules for converting digits to words
            case $number < 0:
                $prefix = "negative";
                $suffix = num_to_text(-1 * $number);
                $string = $prefix . " " . $suffix;
                break;
            case 1:
                $string = "one";
                break;
            case 2:
                $string = "two";
                break;
            case 3:
                $string = "three";
                break;
            case 4:
                $string = "four";
                break;
            case 5:
                $string = "five";
                break;
            case 6:
                $string = "six";
                break;
            case 7:
                $string = "seven";
                break;
            case 8:
                $string = "eight";
                break;
            case 9:
                $string = "nine";
                break;
            case 10:
                $string = "ten";
                break;
            case 11:
                $string = "eleven";
                break;
            case 12:
                $string = "twelve";
                break;
            case 13:
                $string = "thirteen";
                break;
            // fourteen handled later
            case 15:
                $string = "fifteen";
                break;
            case $number < 20:
                $string = num_to_text($number % 10);
                // eighteen only has one "t"
                if ($number == 18) {
                    $suffix = "een";
                } else {
                    $suffix = "teen";
                }
                $string .= $suffix;
                break;
            case 20:
                $string = "twenty";
                break;
            case 30:
                $string = "thirty";
                break;
            case 40:
                $string = "forty";
                break;
            case 50:
                $string = "fifty";
                break;
            case 60:
                $string = "sixty";
                break;
            case 70:
                $string = "seventy";
                break;
            case 80:
                $string = "eighty";
                break;
            case 90:
                $string = "ninety";
                break;
            case $number < 100:
                $prefix = num_to_text($number - $number % 10);
                $suffix = num_to_text($number % 10);
                $string = $prefix . "-" . $suffix;
                break;
            // handles all number 100 to 999
            case $number < pow(10, 3):
                // floor return a float not an integer
                $prefix = num_to_text(intval(floor($number / pow(10, 2)))) . " hundred";
                if ($number % pow(10, 2))
                    $suffix = " and " . num_to_text($number % pow(10, 2));
                $string = $prefix . $suffix;
                break;
            case $number < pow(10, 6):
                // floor return a float not an integer
                $prefix = num_to_text(intval(floor($number / pow(10, 3)))) . " thousand";
                if ($number % pow(10, 3))
                    $suffix = num_to_text($number % pow(10, 3));
                $string = $prefix . " " . $suffix;
                break;
            case $number < pow(10, 9):
                // floor return a float not an integer
                $prefix = num_to_text(intval(floor($number / pow(10, 6)))) . " million";
                if ($number % pow(10, 6))
                    $suffix = num_to_text($number % pow(10, 6));
                $string = $prefix . " " . $suffix;
                break;
            case $number < pow(10, 12):
                // floor return a float not an integer
                $prefix = num_to_text(intval(floor($number / pow(10, 9)))) . " billion";
                if ($number % pow(10, 9))
                    $suffix = num_to_text($number % pow(10, 9));
                $string = $prefix . " " . $suffix;
                break;
            case $number < pow(10, 15):
                // floor return a float not an integer
                $prefix = num_to_text(intval(floor($number / pow(10, 12)))) . " trillion";
                if ($number % pow(10, 12))
                    $suffix = num_to_text($number % pow(10, 12));
                $string = $prefix . " " . $suffix;
                break;
            // Be careful not to pass default formatted numbers in the quadrillions+ into this function
            // Default formatting is float and causes errors
            case $number < pow(10, 18):
                // floor return a float not an integer
                $prefix = num_to_text(intval(floor($number / pow(10, 15)))) . " quadrillion";
                if ($number % pow(10, 15))
                    $suffix = num_to_text($number % pow(10, 15));
                $string = $prefix . " " . $suffix;
                break;
        }
    } else {
        echo "ERROR with - $number
 Number must be an integer between -" . number_format($max_size, 0, ".", ",") . " and " . number_format($max_size, 0, ".", ",") . " exclussive.";
    }
    return $string;
}

echo num_to_text(157187);
```
