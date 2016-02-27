# PHP Exashare API
A Web Service for the Exashare API

## VERSION API
0.01

## DEPENDENCIES

##### File ExashareAPI.php

This API use file_get_contents, you need to enable 'allow_url_fopen' in php.ini

##### File ExashareAPICurl.php

This API use cURL, you need to enable lib curl, [http://php.net/manual/en/curl.installation.php](http://php.net/manual/en/curl.installation.php)

Account Info
------------

```
<?php
include 'ExashareAPI.php';

$api = new ExashareAPI;

$result = $api->AccountInfo(
  [
    key => '1kdgzttjfyzxcg'
  ]
);

if(!$result->{error}){
    echo 'Login: ' . $result->{login};
    echo '<br />';
    echo 'Money: ' . $result->{money};
}else{
    echo $result->{error};
}
?>
```
