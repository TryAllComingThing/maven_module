# maven_module
Maven common module
###一、Maven部署一个文件到仓库
1.本地仓库命令
```
mvn install:install-file -Dfile=[your file] -DgroupId=[xxxx] -DartifactId=[xxxx] -Dversion=[xxxx] -Dpackaging=[pom|jar|other]
```
2.远程仓库命令
```
mvn deploy:deploy-file -Dfile=[your file] -DgroupId=[xxxx] -DartifactId=[xxxx] -Dversion=[xxxx] -Dpackaging=[pom|jar|other] -DrepositoryId=[id] -Durl=[repo url] 
```
###二、本地仓库Git命令
```
$ cd ~/.m2/repository
$ git add -f com/github/${github_account}/${artifactId}/${version}
$ git commit -m 'snapshot of com.github.${github_account}:${artifactId}:${version}'
$ git push origin snapshot
```
###三、使用说明
```
<dependencyManagement>
    <dependencies>
        <dependency>
            <groupId>com.github.sam</groupId>
            <artifactId>spring-framework-bom</artifactId>
            <version>1.0.0.RELEASE</version>
            <type>pom</type>
            <scope>import</scope>
        </dependency>
    </dependencies>
</dependencyManagement>
```
