# wine-api

## Description
This API was made for a school project.

When you call this API with a GET parameter called 'plat' (french), 
it forwards you a JSON file that permits you to print a carousel message in Facebook,
composed of wines that can go with that plate.
Each element have the name of the wine, a picture (got with file_get_html on bing), 
and a link to our website, http://produitsdutiroir.fr

## Params Inc file
The 'params.inc.php' is missing : you need to create one with your server credentials :
```php
  $servername = "hostExample.com";
  $username = "username";
  $password = "password";
  $dbname = "DatabaseName";
```

## Database 
This project uses the provided wines.sql database.
This database comes from [here](https://www.data.gouv.fr/fr/datasets/accords-mets-et-vins/) and was parsed from the CSV file.
The columns used for this projects are 'Nom du mets' (plate name) and 'Nom du vin' (wine name).

## Example
For example, for the call : getwine.php?plat=oeuf, it returns you the folowwing JSON : 
```json
{
  "messages":
  [
    {
      "attachment":
      {
        "type":"template",
        "payload":
        {
          "template_type":"generic",
          "elements":
          [
            {
              "title":"+Aloxe+Corton",
              "image_url":"http:\/\/tse3.mm.bing.net\/th?id=OIP.M730e1b075318f48163d3e36dc899df06o0&w=230&h=170&rs=1&pcl=dddddd&pid=1.1",
              "buttons":
              [
                {
                  "type":"web_url",
                  "url":"http:\/\/produitsdutiroir.fr\/",
                  "title":"Voir sur le site"
                }
              ]
            },
            {
              "title":"Pauillac",
              "image_url":"http:\/\/tse4.mm.bing.net\/th?id=OIP.M437407ec080e19d91c1d9dec0ff88d64o0&w=230&h=170&rs=1&pcl=dddddd&pid=1.1",
              "buttons":
              [
                {
                  "type":"web_url",
                  "url":"http:\/\/produitsdutiroir.fr\/",
                  "title":"Voir sur le site"
                }
              ]
            },
            {
              "title":"Ch%E2teauneuf+du+Pape",
              "image_url":"http:\/\/tse1.mm.bing.net\/th?id=OIP.M8621b027dc5a94fe6db6c3ccf2b85080o0&w=230&h=170&rs=1&pcl=dddddd&pid=1.1",
              "buttons":
              [
                {
                  "type":"web_url",
                  "url":"http:\/\/produitsdutiroir.fr\/",
                  "title":"Voir sur le site"
                }
              ]
            },
            {
              "title":"Santenay",
              "image_url":"http:\/\/tse3.mm.bing.net\/th?id=OIP.M037b89254b90ba1a2be818cbf07e74f2o0&w=230&h=170&rs=1&pcl=dddddd&pid=1.1",
              "buttons":
              [
                {
                  "type":"web_url",
                  "url":"http:\/\/produitsdutiroir.fr\/",
                  "title":"Voir sur le site"
                }
              ]
            },
            {
              "title":"Pommard",
              "image_url":"http:\/\/tse1.mm.bing.net\/th?id=OIP.Ma9bda2d089a5c3c31f1990d066509aa0o0&w=230&h=170&rs=1&pcl=dddddd&pid=1.1",
              "buttons":
              [
                {
                  "type":"web_url",
                  "url":"http:\/\/produitsdutiroir.fr\/",
                  "title":"Voir sur le site"
                }
              ]
            }
          ]
        }
      }
    }
  ]
}
```
