# CI/CD using jenkins and aws
1) create IAM user and give it the required privileges to access s3 bucket and upload contents to it

![screenshot-01](https://user-images.githubusercontent.com/68178003/100717221-72f0fc80-33c2-11eb-889c-be51b4e124c4.png)

2)Install Jenkins On amazon ec2 instance Ubuntu
Here are the key commands for installation:

wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
When the key is added, the system returns OK. Next, append the Debian package repo address to the server's sources.list:

sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
When both of these are all set, run update so that apt will use the new repo:

sudo apt update
Lastly, install Jenkins and its dependencies:

sudo apt install jenkins
Since systemctl doesn't produce output, you can use its status command to confirm that Jenkins began successfully:

sudo systemctl status jenkins

3)Set Up Jenkins

![screenshot-03](https://user-images.githubusercontent.com/68178003/100717251-7a180a80-33c2-11eb-956a-b74e6d04a4c9.png)

4) Install Blue Ocean plugin

![screenshot-04](https://user-images.githubusercontent.com/68178003/100717262-7f755500-33c2-11eb-99ba-3afdb8f25db5.png)

5) build from index.html file using jenkins

![screenshot-05](https://user-images.githubusercontent.com/68178003/100717281-856b3600-33c2-11eb-988d-9f51e9997d0c.png)

![screenshot-06](https://user-images.githubusercontent.com/68178003/100717377-9fa51400-33c2-11eb-8c24-1f526e2de5c8.png)


6) add linting while there is error in the file to ensure linting works correctly

![screenshot-07](https://user-images.githubusercontent.com/68178003/100717360-99af3300-33c2-11eb-8bca-cc48021c2e5c.png)


7) correct the error in the index.html and add upload to aws s3 bucket step instead of build to upload hello world static website hosting to s3 bucket after linting works correcly

![screenshot-08](https://user-images.githubusercontent.com/68178003/100717369-9caa2380-33c2-11eb-8986-94c8064f6159.png)
