# XOR Encryption
In cryptography, XOR Encryption, also known as XOR Cipher, is a encryption algorithm. With this algorithm, a string of text can be encrypted by applying the bitwise XOR operator to every character using a given key. To decrypt the output, merely reapplying the XOR function with the key will remove the cipher.
```php
function XORCipher($data, $key) {
	$dataLen = strlen($data);
	$keyLen = strlen($key);
	$output = $data;

	for ($i = 0; $i < $dataLen; ++$i) {
		$output[$i] = $data[$i] ^ $key[$i % $keyLen];
	}

	return $output;
}
```
### Example
```php
$text = "The quick brown fox jumps over the lazy dog.";
$key = "secret";
$cipherText = XORCipher($text, $key);
$plainText = XORCipher($cipherText, $key);
```
### Output
```php
cipherText: "'\r\u0006R\u0014\u0001\u001a\u0006\bR\a\u0006\u001c\u0012\rR\u0003\u001b\vE\t\a\b\u0004\0E\f\u0004\0\u0006S\u0011\v\u0017E\u0018\u0012\u001f\u001aR\u0001\u001b\u0014K"
plainText: "The quick brown fox jumps over the lazy dog."
```
