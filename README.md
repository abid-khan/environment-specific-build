Maven environment specific configuration
========================================
In this blog I will explain how we can build warfile with environment specific configuration.

Assume we have two different environments stagging and production. Every time we want to  build war for these environment, it is expected that configuration file(here it is application.properties) for the target environment is comes with war file.

Prerequisite
============
Maven


Our configuration file is present  as shown in screen shot.


This this blog we will see how we can use profile to achieve goal.  We will define
*local
*stagging
*production

local
=====
This is a default profile. This is used in eclipse

stagging
========
This profile is used to build war for stagging

production
==========
This profile is used to build war for production


```xml
<profiles>
		<profile>
			<id>local</id>
			<activation>
				<activeByDefault>true</activeByDefault>
			</activation>
		</profile>
		<profile>
			<id>stagging</id>
			<properties>
				<env>stagging</env>
			</properties>
		</profile>
		<profile>
			<id>production</id>
			<properties>
				<env>production</env>
			</properties>
		</profile>
	</profiles>
```

