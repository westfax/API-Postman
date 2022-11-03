##PHP (CURL) Example
**This is an example of our Fax_SendFax command using PHP via Curl command. You can use other PHP libraries to call Restful api calls but this one works great.**

`<?php    
$curl = curl_init();     
curl_setopt_array($curl, array(      
  CURLOPT_URL => 'https://api2.westfax.com/REST/Fax_Send/json',     
  CURLOPT_RETURNTRANSFER => true,     
  CURLOPT_ENCODING => '',     
  CURLOPT_MAXREDIRS => 10,     
  CURLOPT_TIMEOUT => 0,     
  CURLOPT_FOLLOWLOCATION => true,     
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,     
  CURLOPT_CUSTOMREQUEST => 'POST',     
  CURLOPT_POSTFIELDS => array('Username' => '{{User}}','Password' => '{{Pass}}','ProductId' => '{{ProdId}}','Numbers1' => '888-555-1212','Files0'=> new CURLFILE('/path/to/file.pdf')),     
  CURLOPT_HTTPHEADER => array('ContentType: multipart/form-data'),     
));     
$response = curl_exec($curl);     
curl_close($curl);     
echo $response;     
`   
