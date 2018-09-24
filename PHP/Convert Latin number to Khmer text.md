# Convert Latin number to Khmer text
```php
<?php

function num_to_kh_text($complete_char, $enableThousand) {

    //function for split uft8 character
    function mb_str_split($string) {
    //Split at all position not after the start: ^
    //and not before the end: $
        return preg_split('/(?<!^)(?!$)/u', $string);
    }

    //remove left zeros
    $cleanStr = ltrim($complete_char, '0');
    //split number/string to array
    $num_arr = mb_str_split($cleanStr);
    $translated = '';
    $addThousand = false;
    //string array
    $khNUMTxt = array('', 'មួយ', 'ពីរ', 'បី', 'បួន', 'ប្រាំ');
    $twoLetter = array('', 'ដប់', 'ម្ភៃ', 'សាមសិប', 'សែសិប', 'ហាសិប', 'ហុកសិប', 'ចិតសិប', 'ប៉ែតសិប', 'កៅសិប');
    $khNUMLev = array('', '', '', 'រយ', 'ពាន់', 'មឿន', 'សែន', 'លាន');
    $khnum = array('០', '១', '២', '៣', '៤', '៥', '៦', '៧', '៨', '៩');
    //loop to check each number character
    foreach ($num_arr as $key => $value) {
        //convert khmer number to latin number if found
        if (in_array($value, $khnum)) {
            $value = array_search($value, $khnum);
        }
        //allow only number
        if (!is_numeric($value)) {
            return '';
        }
        //check what pos the charactor in
        $pos = count($num_arr) - ($key);
        if ($pos > count($khNUMLev) - 1) {
            $pos = ($pos % count($khNUMLev)) + 2;
        }
        //enable or diable read in thousand
        if ($enableThousand and ( $pos == 5 or $pos == 6)) {
            $pos = $pos - 3;
        }
        //concatenate number as text
        if ($pos == 2) {
            $translated .= $twoLetter[$value];
        } else {
            if ($value > 5) {
                $translated .= $khNUMTxt[5] . $khNUMTxt[$value - 5];
            } else {
                $translated .= $khNUMTxt[$value];
            }
        }
        //work for thousand
        if ($pos == 2 or $pos == 3 or $pos == 4) {
            if ($value > 0) {
                $addThousand = true;
            }
        }
        //concatenate number level
        if ($value > 0 or ( $pos == 4 and $addThousand and $enableThousand) or $pos == 7) {
            $translated .= $khNUMLev[$pos];
        }
        //make addthousand to default value (false)
        if ($pos == 4) {
            $addThousand = false;
        }
    }
    //return the complete number in text
    return $translated;
}

echo num_to_kh_text("100998877", true);

```
