
Introduction
============

This contains a common parent for all projects to use.

Releasing Projects
==================

The release profile enables the maven-gpg-plugin, maven-source-plugin and the license-maven-plugin. Note that the license-maven-plugin ( See [here](http://code.mycila.com/license-maven-plugin) ) has a standard format for licenses. An alternative format for the Apache 2 license is available by specifiying

    <plugin>
        <groupId>com.mycila</groupId>
        <artifactId>license-maven-plugin</artifactId>
        <configuration>
           <header>APACHE-2-SIMPLIFIED-COPYRIGHT.txt</header>
        </configuration>
    </plugin>

in the project configuration. The allows `Copyright (C) ${project.inceptionYear} ${owner}` instead of `Copyright (C) ${project.inceptionYear} ${owner} (${email})`.

Releasing the releng-tools project
==================================

As the license-plugin must have the license module as a dependency, a project variable is used. This means that when releasing this variable **must** be specified e.g.

    mvn -DdryRun=true release:prepare -DglobalVersion=<next release version>
