
# Run Java Application as a Background Process in Ubuntu OS
<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/java/java-original-wordmark.svg" title="Java" alt="Java" width="80" height="80"/>&nbsp;
</div>

So let's start
If You are not installed jdk on machine first install install




## Deployment

To deploy this project run

```bash
  sudo apt install default-jdk
```
```bash
  javac --version
```
Create your Java Project jar file and run following command to check whether java app running as foreground process
```bash
  java -jar /web/java_app.jar
```
If running successfully then you are ready to run your java application as background process, terminate this foreground process 
So now we start Configuring file for Background process



## Step 1:
Find your user defined services mine was at 
```bash
  cd /etc/systemd/system/
```
Create file by giving command
```bash
  nano java_service.service
```
Copy or Write following code in your nano editor, save and close it
Note: ExecStart= after -jar give your java app jar file absolute path
```bash
[Unit]
Description=A Demo Java Application Daemon Process

[Service]
ExecStart=/usr/bin/java -jar /home/java_code/java_app.jar
User=user

[Install]
WantedBy=multi-user.target
```
Give the Permission of your jar file to execute by other
```bash
 chmod 777 /home/java_code/java_app.jar
 ```
 Now You are ready to run your ApplicationNow give Following command to start Process
 ```bash
  systemctl enable java_service
  ```
  ```bash
   systemctl start java_service
  ```
  To see status of your Process
   ```bash
   systemctl status java_service
  ```
  To stop Process
  ```bash
systemctl status java_service
  ```
  And That's it,
  Congratulations, your are done

