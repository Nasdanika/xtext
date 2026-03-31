# Xtext

Shaded wrapper of Xtext, Xtext util and Xtext ecore to make them available for JPMS.

* Use `jpms-ready` qualified 
* Add exclusions for the source modules to dependencies which use them
* Add log4j dependencies

See the example below:

```xml
<dependencies>
    <dependency>
        <groupId>org.nasdanika</groupId>
        <artifactId>xtext</artifactId>
        <classifier>jpms-ready</classifier>
        <version>2.42.0</version>
    </dependency>
    <dependency>
        <groupId>org.eclipse.emf</groupId>
        <artifactId>org.eclipse.emf.ecore.xcore</artifactId>
        <version>1.36.0</version>
        <exclusions>
            <exclusion>
                <groupId>org.eclipse.xtext</groupId>
                <artifactId>org.eclipse.xtext</artifactId>
            </exclusion>
            <exclusion>
                <groupId>org.eclipse.xtext</groupId>
                <artifactId>org.eclipse.xtext.util</artifactId>
            </exclusion>
        </exclusions>
    </dependency>
    <dependency>
        <groupId>org.eclipse.emf</groupId>
        <artifactId>org.eclipse.emf.ecore.xcore.lib</artifactId>
        <version>1.7.1</version>
    </dependency>
    <dependency>
        <groupId>org.apache.logging.log4j</groupId>
        <artifactId>log4j-api</artifactId>
        <version>2.25.4</version>
    </dependency>
    <dependency>
        <groupId>org.apache.logging.log4j</groupId>
        <artifactId>log4j-core</artifactId>
        <version>2.25.4</version>
    </dependency>
    <dependency>
        <groupId>org.apache.logging.log4j</groupId>
        <artifactId>log4j-1.2-api</artifactId>
        <version>2.25.4</version>
    </dependency>
</dependencies>
```

Also add the below repository definition:

```xml
<!-- For Xtext wrapper -->    
<repositories>
    <repository>
        <id>nasdanika-releases</id>
        <url>https://maven.nasdanika.org/releases</url>
    </repository>
</repositories> 
```