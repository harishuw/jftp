# Jftp

Jftp is java plugin used to upload files to server using ftp.After first upload it will automatically detects changed file so that next time it will upload changed files only.
### Requirments
Latest version of java
### Config file
Ftp details should be stored in json file jftpconfig.json
```
{
    "default": "config1",
    "config1":{
        "host":"ftp.example.com",
        "username":"user",
        "password":"password",
        "port":"21",
        "localroot":"C://xampp/htdocs/someproject",
        "serverroot":"public_html/something"
		"ignore":[
            "/some/file",
			"/some/folder"
        ]
    }
}
```
  - defaut: default config
  - host:host name of server
  - username: username
  - passwoed:password
  - port:port
  - localroot: root location of local files
  - serverroot: root location of server files where you want to upload
  - ignore: files you want to ignore from uploading
### Usage

```sh
java -jar jftpv1.0.1.jar <argument1> <argument2>...
```

### Available options are
- Upload files to server
    ```
    java -jar jftpv1.0.1.jar
    
    java -jar jftpv1.0.1.jar config1
    ```
    - First will upload `default` config items to server 
    - Second will upload items with config name  `config1` to server
- Mark files as uploaded
    ```
    java -jar jftpv1.0.1.jar -uploaded
    
    java -jar jftpv1.0.1.jar -uploaded config1
    ```
     - First will mark `default` config items to as uploaded and will not upload to server  
    - Second will mark items with config name `config1`  as uploaded and will not upload to server  
- Status
    ```
    java -jar jftpv1.0.1.jar -status
    
    java -jar jftpv1.0.1.jar -status config1
    ```
    - First will show status of `default` config
    - Second will show status of items with config name `config1`
- Test ftp credentials
    ```
    java -jar jftpv1.0.1.jar -test
    
    java -jar jftpv1.0.1.jar -test config1
    ```
    - First will test ftp  of `default` config
    - Second will test ftp  of of item with config name `config1`
- Get version
  ```
    java -jar jftpv1.0.1.jar -v
    
    java -jar jftpv1.0.1.jar -version
    ```
- Get help
  ```
    java -jar jftpv1.0.1.jar -h
    
    java -jar jftpv1.0.1.jar -help
    ```
    

License
----
MIT
