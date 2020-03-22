# java8-docker-memory-managament-references

#Command used as an examples:
1) Creating containers

`docker run --name java8 -t -d --memory=100m --entrypoint "/bin/sh" java:openjdk-8-alpine`

`docker run --name java8-212 -t -d --memory=100m --entrypoint "/bin/bash" openjdk:8u212-jre`

`docker run --name java10 -t -d --memory=100m --entrypoint "/bin/bash" openjdk:10-jdk`

2) Running commands

`docker exec -it java8 java -XX:+PrintFlagsFinal -version | grep MaxHeapSize`

`docker exec -it java8 java -XX:+PrintFlagsFinal -version | grep -w "UseContainerSupport"`

`docker exec -it java8-212 java -XX:+PrintFlagsFinal -version | grep -w "MaxHeapSize"`

`docker exec -it java8-212 java -XX:+PrintFlagsFinal -version | grep -w "UseContainerSupport"`

`docker exec -it java10 java -XX:+PrintFlagsFinal -version | grep MaxHeapSize`

`docker exec -it java10 java -XX:+PrintFlagsFinal -version | grep -w "UseContainerSupport"`

#References:

https://www.linuxjournal.com/content/everything-you-need-know-about-linux-containers-part-i-linux-control-groups-and-process

https://royvanrijn.com/blog/2018/05/java-and-docker-memory-limits/

https://betsol.com/java-memory-management-for-java-virtual-machine-jvm/

https://dzone.com/articles/java-memory-management

https://dzone.com/articles/java-8-permgen-metaspace

https://banzaicloud.com/blog/java-resource-limits/

https://medium.com/faun/understanding-docker-container-memory-limit-behavior-41add155236c

http://matthewkwilliams.com/index.php/2016/03/17/docker-cgroups-memory-constraints-and-java-cautionary-tale/

https://fabiokung.com/2014/03/13/memory-inside-linux-containers/
