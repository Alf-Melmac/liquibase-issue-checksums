# liquibase-issue-checksums
Minimally reproducible example of changed checksums in changesets with SQL statements specifying a different DBMS than the one currently in use.

## Steps
1. Execute `mvn liquibase:update`
2. Update liquibase.version in `pom.xml` to current version 4.23.2
3. Execute `mvn liquibase:update` again
4. Error:
```
src/main/resources/changelog.xml::2.broken.a::test was: 8:35070114bee42b11860c8f936a360a7b but is now: 8:d41d8cd98f00b204e9800998ecf8427e
src/main/resources/changelog.xml::2.broken.b::test was: 8:35070114bee42b11860c8f936a360a7b but is now: 8:d41d8cd98f00b204e9800998ecf8427e
src/main/resources/changelog.xml::3.broken::test was: 8:91f6a55bd7eb7aade3e7a9148a678fd4 but is now: 8:35070114bee42b11860c8f936a360a7b
src/main/resources/changelog.xml::4.broken::test was: 8:35070114bee42b11860c8f936a360a7b but is now: 8:d41d8cd98f00b204e9800998ecf8427e
```
