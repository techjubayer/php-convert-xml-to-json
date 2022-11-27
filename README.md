# php-convert-xml-to-json
XML encoding="utf-16" convert into JSON format in PHP


```php
function xmlToJsonConverter($reqString){
    $response = str_replace("utf-16", "utf-8", $reqString);
    $response = htmlspecialchars_decode($response, ENT_QUOTES);
    $response = simplexml_load_string($response);
    $response = json_encode($response);
    $response = json_decode($response, true);
    return $response;  
}
```
