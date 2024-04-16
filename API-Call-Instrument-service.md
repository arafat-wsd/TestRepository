# Instrument Service

## API Name
~~~
/page-api/instruments/v2/{site-variant}/details/{identifier}/{value}
~~~

## Steps to test it

- Choose a valid config project (e.g `ubs-keyinvest-za-config`)
- copy the path of this config project
- open `WSL` 
- `cd ~`
- create symbolic link by running:
     `ln -s config_project_directory /tmp/instrument-service-config`
- check it by running. few `yaml` files will show up.
    ls /tmp/instrument-service-config
- Turn on Azure vpn client connection
- Run the instrument service project 
- go to localhost:8080
- Try this api: `/page-api/instruments/v2/{site-variant}/details/{identifier}/{value}`
- Find out site-variant from `site.yaml` file of the config project you have choosen
- Find out identifier from `identifiers.yaml` file of the config file (mostly: isin, wkn)
- To find out value of identifier go to [sf-client](https://sf-client.fra1.framework/instrument) (chrome browser is recommended)
-  Choose suitable API User(e.g `Ubs-Keyinvest`) according to the config project
- Click on `Query` Tab in the page
- Enter a `Structure Id`. You will get it from `groups.yaml` file of config project
- Choose `States` to `active`
- Choose `Tags`. You will find it from `site.yaml` file of config project
- Click the `search` button

A list will show up in the bottom of the page if result found. Click on any of it and copy the identifier value and paste it in the `value` field of the `api` call.

i.e `ZAE000322616` is an identifier value
