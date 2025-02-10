# Basic Maven Commands
| Command | Function |
| :---: | :--- |
| `mvn clean` | Remove target directory, which contains compiled classes, test results and the final JAR/WAR file. |
| `mvn install` | Install packaged artifact (JAR, WAR) into local Maven repository. |
| `mvn clean install` | Combines `mvn clean` and `mvn install`. |
| `mvn compile` | Compile the source code into Java bytecode (class files). |
| `mvn test` | Execute unit tests defined in project. |
| `mvn package` | Create final package for project according to the type defined in `pom.xml`. |
| `mvn deploy` | Deploy packaged artifact to remote repository. |