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

Add URL Upload
--------------

```

<?php
include 'ExashareAPI.php';

$api = new ExashareAPI;

$result = $api->UploadURL(
  [
    key => '1kdgzttjfyzxcg',
    url => 'http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4',
    folder => 'name_your_folder'
  ]
);

if(!$result->{error}){
    echo 'Queue ID: ' . $result->{queue_id};
}else{
    echo $result->{error};
}
?>

```

Check URL Upload
----------------

```

<?php
include 'ExashareAPI.php';

$api = new ExashareAPI;

$result = $api->CheckUploadURL(
  [
    key => '1kdgzttjfyzxcg',
    id => 'queue_id'
  ]
);

if(!$result->{error}){
    echo 'Status: ' . $result->{status};
    echo '<br />';
    echo 'URL: ' . $result->{url};
    echo '<br />';
    echo 'File Code: ' . $result->{file_code};
    echo '<br />';
}else{
    echo $result->{error};
}
?>

```
