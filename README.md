
Spring Boot

After creating several ways of web applications, I really found easy way to create a web application with Spring Boot.

Spring frame work is great frame work for dependency injection and configuration managements.
Spring boot is great tool for creating Rapid applications with providing security.

Here I will explain my sample rest web app with details



POM.xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<groupId>com.test</groupId>
	<artifactId>SpringBootSample</artifactId>
	<packaging>jar</packaging>
	<version>0.0.1-SNAPSHOT</version>
	<name>SpringBootSample</name>

	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>1.5.1.RELEASE</version>
	</parent>
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
	</dependencies>
</project>

application.properties

server.port=9090
server.contextPath=/rest


Spring Boot Java

package com.sample;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RestController;

/**
 * @author Balaji Achanta
 *
 */
@SpringBootApplication
@RestController
public class SpringBootSample {


	public static void main(String[] args) {

		SpringApplication.run(SpringBootSample.class, args);

		System.out.println("********* started *****");
	}

	@RequestMapping(value="/test", produces={"application/json"},  method = RequestMethod.GET)
	public String helthCheck() 
	{
		return "{\"msg\":\"hello world\"}";
	}
}




http://localhost:9090/rest/test

{
  "msg": "hello world"
}
