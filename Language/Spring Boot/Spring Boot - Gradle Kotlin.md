# What is Gradle ?
# Gradle Spring-Boot plugins
- To build Spring-Boot application with gradle we need to add two plugins to the build.gradle
- First, id(org.springframework.boot) version "3.4.1"
- Second, id("io.spring.dependency-management") version "1.1.7"
These two plug ins bring neccessary dependencies and the prebuilt Gradle configuration which has several tasks to build and run spring boot application. 

- And don't forget java plugin itself
``` kotlin
plugins{
	java
	id("org.springframework.boot") version "3.4.1"
	id("io.spring.dependency-management") version "1.1.7"
}
```

# Setup java toolchain
``` kotlin
	java{
		toolchain{
				languageVersion = JavaLanguageVersion.of(21)	
		}
	}
```

- Gradle utilizes java toolchain to get neccessary java information of the computer
# Spring-Boot with Lombok
- To use lombok we need to configure the annotationProcessor before we add dependency
```
configurations{
	compileOnly{
		extendsFrom(configurations.annotationProcessor.get())
	}
}
```
Above is Kotlin version of configuration, so if you need groovy style you need to google it to get correct syntax for the groovy style.

