# samba-server2

This Alpine Linux container publish a samba server with an authentication


## Enviromment variables Groups:

**SMB_USER, SMB_PASS, SMB_SHARE** refers to the credentials and share name to expose.


## yml example:

    version: '3.6'
    services:
      smb_server2:
        image: tamuxx/samba-server2
        container_name: smb_server2
        restart: unless-stopped
        hostname: smb_server2
        environment:
            - SMB_USER=username
            - SMB_PASS=password
            - SMB_SHARE=share_name_to_publish
        volumes:
            - /data_to_share/:/mnt
        ports:
            - 139
            - 445
