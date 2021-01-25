# vaadin-jandex

Builds the Jandex index of all Vaadin core libraries. This enables Vaadin-based
apps to run on top of Quarkus+Undertow.

There are two artifacts built:

* [vaadin-core-jandex](vaadin-core-jandex) builds the Jandex index for `vaadin-core` (only
  the open-source components)
* [vaadin-jandex](vaadin-jandex) builds the Jandex index for `vaadin`
  (both the open-source components and the pro components such as Board, GridPro,
  CRUD etc).

## How to use

1. git clone the project
2. Edit `gradle.properties` and modify the Vaadin version to the version of your choice.
3. Run `./gradlew publishToMavenLocal`. The library is now installed in your local repo.
4. git clone https://github.com/mvysny/vaadin-quarkus
5. Modify the vaadin-quarkus's `pom.xml` and add the dependency on this library:

```xml
<dependency>
  <groupId>com.github.mvysny.vaadin-jandex</groupId>
  <artifactId>vaadin-jandex</artifactId>
  <version>14.4.6</version>
</dependency>
```

6. Edit the vaadin-quarkus's `application.properties` and delete all Vaadin-related
   `.index-dependency.` lines.
7. Run the vaadin-quarkus project - it should now start as usual.

## License

See [License](LICENSE.txt).
