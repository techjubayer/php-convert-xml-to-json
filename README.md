# php-convert-xml-to-json
XML encoding="utf-16" convert into JSON format in PHP

<?php


function xmlToJsonConverter($reqString){
    $response = str_replace("utf-16", "utf-8", $reqString);
    $response = htmlspecialchars_decode($response, ENT_QUOTES);
    $response = simplexml_load_string($response);
    $response = json_encode($response);
    $response = json_decode($response, true);
    return $response;  
}


$xmlString = '<?xml version="1.0" encoding="utf-16"?>
                  <User>
                    <Name>Jubayer Ali</Name>
                    <Age>26</Age>
                     <Email>techjubayer@gmail.com</Email>
                  </User>';

$jsonArray = xmlToJsonConverter($xmlString);

 echo 'Name:- '.$jsonArray['Name'].'<br>Age:- '.$jsonArray['Age'] .'<br>Email:- '.$jsonArray['Email'] ;

?>
