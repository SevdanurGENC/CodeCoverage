# CodeCoverage
An example of using jacoco on about code coverage


![image](https://user-images.githubusercontent.com/5441882/148996985-edd50317-3fc2-4368-a200-69cbd04841d2.png)

![image](https://user-images.githubusercontent.com/5441882/148997020-f11ba9e0-de08-4959-95ca-1f1c14a1457f.png)

![image](https://user-images.githubusercontent.com/5441882/148997050-09fb84cd-1b66-4569-b28f-3017febeee55.png)

![image](https://user-images.githubusercontent.com/5441882/148997078-b1582fdf-e53e-4343-87a4-d523af0c6292.png)
 
```java
<build>
        <plugins>
            <plugin>
                <groupId>org.jacoco</groupId>
                <artifactId>jacoco-maven-plugin</artifactId>
                <version>0.7.9</version>
                <executions>
                    <execution>
                        <id>default-prepare-agent</id>
                        <goals>
                            <goal>prepare-agent</goal>
                        </goals>
                    </execution>
                    <execution>
                        <id>default-report</id>
                        <phase>prepare-package</phase>
                        <goals>
                            <goal>report</goal>
                        </goals>
                    </execution>
                    <execution>
                        <id>default-check</id>
                        <goals>
                            <goal>check</goal>
                        </goals>
                        <configuration>
                            <rules><!-- implementation is needed only for Maven 2 -->
                                <rule implementation="org.jacoco.maven.RuleConfiguration">
                                    <element>BUNDLE</element>
                                    <limits><!-- implementation is needed only for Maven 2 -->
                                        <limit implementation="org.jacoco.report.check.Limit">
                                            <counter>COMPLEXITY</counter>
                                            <value>COVEREDRATIO</value>
                                            <minimum>0.01</minimum>
                                        </limit>
                                    </limits>
                                </rule>
                            </rules>
                        </configuration>
                    </execution>
                </executions>
            </plugin>
            
        </plugins>
        </build>
```
