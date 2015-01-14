CGI script to get snapshot taken from raspberry pi and then shown in
browser

Can be deployed as apache CGI script.

```
<VirtualHost *:443>
ServerName server.name

ScriptAlias /get/ /opt/jamocam/

DocumentRoot /tmp/jamocam/

<Directory /opt/jamocam/>
Require all granted
</VirtualHost>Directory>

</>VirtualHost>
```


This provides following api

* /
> Show file listing provided by apache

* /:snapshot
> Show file listing for folder with the name of :id

* /update/
> Takes a snapshot and refirect to /:snapshot

* /update/?night=1
> Takes a snapshot in night expousure and refirect to /:snapshot




And running CGI scripts like this might create unknown
security issues to the machine being used.

For deployment protection with at least http basic auth is
recommended.

