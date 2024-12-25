# To get information of how to 
curl https://start.spring.io

# To get demo.zip as kickstarter
curl https://start.spring.io/starter.zip -d dependencies=lombok,web,jap,validation -d type=gradle-project-kotlin -o demo.zip

# Unzip
unzip domo.zip -d demo

# Running Spring-Boot application
after installing of gradle
gradle build
gradle bootRun