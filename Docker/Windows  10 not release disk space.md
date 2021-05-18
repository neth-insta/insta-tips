# Windows 10 not release disk space fixed:
1. Via the docker ui, Under the images tab hit the cleanup button. 
1. Select both Unused and Dangling and hit the Remove button
1. Run ```docker system prune -a```
1. Close docker desktop
1. Exit anything using wsl, and then from administrator PowerShell run 
    ```wsl --shutdown```
1. In PowerShell Mount the docker ext4 image using:
    ```Mount-VHD -Path C:\Users\[Username]\AppData\Local\Docker\wsl\data\ext4.vhdx -ReadOnly```
1. In PowerShell Mount the docker ext4 image using:
    ```Optimize-VHD -Path C:\Users\[Username]\AppData\Local\Docker\wsl\data\ext4.vhdx -Mode Full```
1. In PowerShell Mount the docker ext4 image using:
    ``` Dismount-VHD C:\Users\[Username]\AppData\Local\Docker\wsl\data\ext4.vhdx``` 