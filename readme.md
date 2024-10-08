## RustDesk Server

### Docker Image

```bash
docker pull rustdesk/rustdesk-server:latest
```

### Run

```bash
mkdir data
docker compose up -d # make sure the ports are available
```

### Verify

```bash
docker ps
```

```bash
netstat -tuln | grep 2111\*
# expected output
tcp6       0      0 :::21118                :::*                    LISTEN     
tcp6       0      0 :::21119                :::*                    LISTEN     
tcp6       0      0 :::21116                :::*                    LISTEN     
tcp6       0      0 :::21117                :::*                    LISTEN     
tcp6       0      0 :::21115                :::*                    LISTEN     
udp        0      0 0.0.0.0:21119           0.0.0.0:*                          
udp6       0      0 :::21116                :::*   
```

### Setup Client

- Open the Network Settings tab
- Add ID server: `<your-server-ip>:21117`
- Add the provided public key(in `data` directory)
- Save

NOTE: Please ensure that the server is reachable from the client. If you are using a
VPN, make sure that the VPN is connected and active.
