#Usage

Once the dependencies have been set, the skin can be used by adding the following element to the site.xml file:

```xml
<skin>
    <groupId>com.wandrell.maven</groupId>
    <artifactId>docs-maven-skin</artifactId>
    <version>${site.skin.version}</version>
</skin>
```

As shown, it is recommended defining the version in the properties section of the POM, which will then be replaced by Maven automatically before creating the site.

## Sample site.xml

The site requires a correctly configured site.xml file to work. For more details check the [site.xml page][site_xml], but the following shows an example of how it should look:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/DECORATION/1.6.0"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/DECORATION/1.6.0 http://maven.apache.org/xsd/decoration-1.6.0.xsd">

    <skin>
        <groupId>com.wandrell.maven</groupId>
        <artifactId>docs-maven-skin</artifactId>
        <version>${site.skin.version}</version>
    </skin>

    <custom>
        <skinConfig>
            <keywords>Maven Site, fix, HTML5</keywords>
            <descriptionUrl>Check the documentation for the Docs Maven Skin</descriptionUrl>
            <twitterSite>@wandrell</twitterSite>
            <interpreters>
                <interpreter>JDK 7</interpreter>
                <interpreter>JDK 8</interpreter>
                <interpreter>OpenJDK 7</interpreter>
            </interpreters>
            <releaseRepositories>
                <releaseRepository>
                    <name>Bintray</name>
                    <url>${bintrayURL}</url>
                </releaseRepository>
                <releaseRepository>
                    <name>Maven Central</name>
                    <url>${mavenURL}</url>
                </releaseRepository>
            </releaseRepositories>
            <topNav>
                <menu>Documentation</menu>
                <menu>Info and reports</menu>
            </topNav>
            <bottomNav>
                <menu>General Info</menu>
            </bottomNav>
            <pages>
                <index>
                    <sections>
                        <body />
                        <columns>2</columns>
                    </sections>
                </index>
            </pages>
        </skinConfig>
    </custom>

    <body>
        <menu name="General Info" inherit="top">
            <item name="Acquire" href="./acquire.html" />
            <item name="Usage" href="./usage.html" />
            <item name="Changes Log" href="./changes-report.html" />
        </menu>
        <menu name="Documentation" inherit="bottom">
            <item name="Acquire" href="./acquire.html" />
            <item name="Usage" href="./usage.html" />
        </menu>
        <menu name="Info and reports" inherit="bottom">
            <item name="Info" href="./info.html" />
            <item name="Reports" href="./reports.html" />
            <item name="JavaDocs" href="./apidocs/" />
        </menu>
    </body>
</project>
```

Note that this example site.xml shown includes some properties which are read from the POM file, such as *${bintrayURL}*.

[site_xml]: ./site_xml.html
