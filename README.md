## 👻Introduce

[SSProbe](https://github.com/realzolo/ssprobe) is a server status monitor that provides a visual interface that displays your server status in real time, such as CPU usage, memory usage, network speed, etc.  **[中文版](https://github.com/realzolo/ssprobe/blob/master/README_CN.md)**

![](https://image.onezol.com/img/ssprobe.jpg)

## 🎉Installation & Usage

### Server

In the [release page](https://github.com/realzolo/ssprobe/releases) to find the **server version** of the corresponding system and download to your server, You can configure your port and token in the `config.yaml` file.  

```yaml
# config.yaml
token: 123456   # Used to authenticate identity.
port:	
  server: 3384   # Server port
  web-api: 9000  # Http request port
```

Make sure both files are in the same directory, then execute the program.

```bash
chmod a+x server
./server

# Or run in the background
nohup ./server &
```



### Client

In the [release page](https://github.com/realzolo/ssprobe/releases) to find the corresponding system of client version and download to your server, and use the following command to start the client program: 

```bash
chmod a+x ./client
./client --name=CLIENT_NAME --server=SERVER_ADDRESS --port=SERVER_PORT --token=YOUR_TOKEN

# Or run in the background
nohup ./client --name=CLIENT_NAME --server=SERVER_ADDRESS --port=SERVER_PORT --token=YOUR_TOKEN &
```

For example: `./client --name=ClientA --server=110.42.133.216 --port=3384 --token=123456`

### Web

Will [web directory](https://github.com/realzolo/ssprobe/tree/master/web) in the file deployed to your HTTP server or other static web site hosting platform. You can in the [config.json](https://github.com/realzolo/ssprobe/blob/master/web/config.json) to change your configuration information. After the deployment is complete, you can go to the monitoring page.  

```json
{
    "API": "ws://server_address:port/json",   
    "SITE_TITLE":"your_site_title" 
}
```

