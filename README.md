# sonarqube-jenkins-integration
## Pre-requisite
### We need to have Jenkins and sonarqube server up and running (by default Jenkins runs on 8080 and sonarqube at 9000)

## 1-Initial setup
### In Jenkins install plugins like docker, sonarqube and Sonar quality gate plugin (manage Jenkins --> manage plugins --> in available tab search for respective plugins) After sonar plugin installation in configure system enter sonar information as shown in below picture
## 2-Server authentication token:
### this token has to be created in sonarqube To create that token in sonarqube navigate to administration --> Security --> Users ( after which you will see list of users)
![image](https://user-images.githubusercontent.com/107158398/178148153-183d1a38-5b37-419f-bb1a-b5328c99287a.png)
### Click on token button, you will prompted to create token as shown in below pictures
![image](https://user-images.githubusercontent.com/107158398/178148186-4b0ee55e-ff9e-4d62-b785-3f0ba480e509.png)

### Give meaningful name and click on generate
![image](https://user-images.githubusercontent.com/107158398/178148209-d31aa4e7-4d72-4cc7-9479-77eedfc70f85.png)

### Copy the token to create secret text in jenkins
![image](https://user-images.githubusercontent.com/107158398/178148258-8f2424c2-e0da-4fa7-8663-4747d9a624b9.png)
### In Jenkins navigate manage Jenkins --> manage credentials --> add credentials --> select kind as secret text --> give value in secret ( will show up in sonar authentication token dropdown)

![image](https://user-images.githubusercontent.com/107158398/178148298-258186a2-124b-4cee-ac3a-4929f4fb686d.png)

### Go to manage Jenkins, system configure, and scroll down looking for sonarqube server
### - check on environment variables
### - click on add sonarqube 
![image](https://user-images.githubusercontent.com/107158398/178148352-81bbe91e-7916-4174-9137-23aa923074a4.png)

#### Name: any meaningful name, but this will be referred in pipeline while executing sonar steps
#### Server URL: sonarqube url
## WebHook:
### Also need to create webhook to have communication between jenkins and sonarqube To create webhook navigate to administration --> configuration --> webhooks --> then provide name and url of your jenkins sufixed with /sonarqube-webhook/
### for example: http://jenkinsipaddress:8080/sonarqube-webhook
![image](https://user-images.githubusercontent.com/107158398/178148430-29f23e1c-5a80-4a73-a875-038be311bda5.png)
### 
