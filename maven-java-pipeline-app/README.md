### Jenkins + GitLab + kubernetes Pipeline流水线构建Java项目
#### 部署Jenkins
```
#kubectl apply -f jenkinsci/jenkinsci.yml
```
#### 制作tomcat镜像
```
#docker build -t harbor.sly.com/library/tomcat8 .
#docker push harbor.sly.com/library/tomcat8
```
#### 制作jenkins-slave镜像
```
#docker build -t harbor.sly.com/library/jenkins-slave-jdk .
#docker push harbor.sly.com/library/jenkins-slave-jdk
```
#### 配置jenkins plpeline项目实现CI/CD
