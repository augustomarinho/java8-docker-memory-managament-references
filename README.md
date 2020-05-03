# java8-docker-memory-managament-references

# Commands used as an examples:
1) Creating containers

`docker run --name java8 -t -d --memory=100m --entrypoint "/bin/sh" java:openjdk-8-alpine`

`docker run --name java8-212 -t -d --memory=100m --entrypoint "/bin/bash" openjdk:8u212-jre`

`docker run --name java8-nolimit -t -d --entrypoint "/bin/sh" java:openjdk-8-alpine`

`docker run --name java9 -t -d --memory=100m --entrypoint "/bin/sh" openjdk:9`

`docker run --name java10 -t -d --memory=100m --entrypoint "/bin/bash" openjdk:10-jdk`

`docker run --name java11 -t -d --memory=100m --entrypoint "/bin/bash" openjdk:11-jdk`

`docker run --name java12 -t -d --memory=100m --entrypoint "/bin/sh" openjdk:12-alpine`

`docker run --name java13 -t -d --memory=100m --entrypoint "/bin/sh" openjdk:13-alpine`

`docker run --name java14 -t -d --memory=100m --entrypoint "/bin/sh" openjdk:14-alpine`

`docker run --name java15 -t -d --memory=100m --entrypoint "/bin/sh" openjdk:15-alpine`


2) Running commands

`docker exec -it java8 java -XX:+PrintFlagsFinal -version | grep MaxHeapSize`

`docker exec -it java8 java -XX:+PrintFlagsFinal -version | grep -w "UseContainerSupport"`

`docker exec -it java8-212 java -XX:+PrintFlagsFinal -version | grep -w "MaxHeapSize"`

`docker exec -it java8-212 java -XX:+PrintFlagsFinal -version | grep -w "UseContainerSupport"`

`docker exec -it java10 java -XX:+PrintFlagsFinal -version | grep MaxHeapSize`

`docker exec -it java10 java -XX:+PrintFlagsFinal -version | grep -w "UseContainerSupport"`

3) Metaspace Studies

`docker exec -it java8 java -XX:+PrintFlagsFinal -version | grep MetaspaceSize`

`docker exec -it java8-nolimit java -XX:+PrintFlagsFinal -version | grep MetaspaceSize`

`docker exec -it java7 java -XX:+PrintFlagsFinal -version | grep MetaspaceSize`

`docker exec -it java12 java -XX:+PrintFlagsFinal -version | grep -w "MetaspaceSize\|MaxMetaspaceSize"`

`docker exec -it java13 java -XX:+PrintFlagsFinal -version | grep -w "MetaspaceSize\|MaxMetaspaceSize"`

`docker exec -it java14 java -XX:+PrintFlagsFinal -version | grep -w "MetaspaceSize\|MaxMetaspaceSize"`

`docker exec -it java15 java -XX:+PrintFlagsFinal -version | grep -w "MetaspaceSize\|MaxMetaspaceSize"`

4) XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap Studies

`docker exec -it java8-212 java -XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap -XX:+PrintFlagsFinal -version | grep MaxHeapSize`

`docker exec -it java8-212 java -XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap -XX:+PrintFlagsFinal -version | grep -w "UseCGroupMemoryLimitForHeap"`

`docker exec -it java8-212 java -XX:+PrintFlagsFinal -version | grep MaxHeapSize`

`docker exec -it java8-212 java -XX:+PrintFlagsFinal -version | grep -w "UseCGroupMemoryLimitForHeap"`

`docker exec -it java8-212 java -XX:+PrintFlagsFinal -version | grep -w "MetaspaceSize\|MaxMetaspaceSize"`

`docker exec -it java9 java -XX:+PrintFlagsFinal -version | grep MaxHeapSize`

`docker exec -it java9 java -XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap -XX:+PrintFlagsFinal -version | grep -w "UseCGroupMemoryLimitForHeap"`

5) -XX:UseContainerSupport Estudies

`docker exec -it java9 java -XX:+PrintFlagsFinal -version | grep -w "UseContainerSupport"`

`docker exec -it java10 java -XX:+PrintFlagsFinal -version | grep -w "UseContainerSupport"`

`docker exec -it java10 java -XX:+PrintFlagsFinal -version | grep MaxHeapSize`

`docker exec -it java8-212 java -XX:+PrintFlagsFinal -version | grep MaxHeapSize`

`docker exec -it java8-212 java -XX:+PrintFlagsFinal -version | grep -w "UseContainerSupport"`

`docker exec -it java10 java -XX:+PrintFlagsFinal -version | grep -w "MetaspaceSize\|MaxMetaspaceSize"`





# References:

https://www.linuxjournal.com/content/everything-you-need-know-about-linux-containers-part-i-linux-control-groups-and-process

https://royvanrijn.com/blog/2018/05/java-and-docker-memory-limits/

https://betsol.com/java-memory-management-for-java-virtual-machine-jvm/

https://dzone.com/articles/java-memory-management

https://dzone.com/articles/java-8-permgen-metaspace

https://banzaicloud.com/blog/java-resource-limits/

https://medium.com/faun/understanding-docker-container-memory-limit-behavior-41add155236c

http://matthewkwilliams.com/index.php/2016/03/17/docker-cgroups-memory-constraints-and-java-cautionary-tale/

https://fabiokung.com/2014/03/13/memory-inside-linux-containers/

https://www.javainuse.com/java/metaspace

http://java-latte.blogspot.com/2014/03/metaspace-in-java-8.html
