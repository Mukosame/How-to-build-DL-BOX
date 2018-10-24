In the root direcotry 

```bash
sudo mkdir /data 
sudo fdisk –l (find the drive you have) 
sudo gedit /etc/fstab 
```

Add theis to the last line: 

```bash
/dev/sdb1 /data ext4 defaults 0 0 
```

Mount the partition: 

```bash
sudo mount /data 
```

 


https://askubuntu.com/questions/125257/how-do-i-add-an-additional-hard-drive 
