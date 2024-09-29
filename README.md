# My App

## Running the application

The project is a standard Maven project. To run it from the command line,
type `mvnw` (Windows), or `./mvnw` (Mac & Linux), then open
http://localhost:8080 in your browser.

## Building your app for Control Center

To create a production build, call `mvnw clean package -Pproduction` (Windows),
or `./mvnw clean package -Pproduction` (Mac & Linux).
This will build a JAR file with all the dependencies and front-end resources,
ready to be deployed. The file can be found in the `target` folder after the build completes.

Then, build the Dockerized version of the project, run

```
mvn clean package -Pproduction
docker build --platform linux/amd64,linux/arm64 -t YOURID/myapp:VERSION .
docker push YOURID/myapp:VERSION
```

Notes
- Replace VERSION with a number
- Replace YOURID with your DockerHub id
- Push will become public. You might want to use a private repository instead.
- You can either omit the `--platform` option and only build for the platfrom your development machine is running on; or [you need to enable multi-platform builds](https://docs.docker.com/build/building/multi-platform/).


## Install control center and deploy the application there

[Deployment instructions](https://vaadin.com/docs/latest/control-center/getting-started) should guide you step-by-step.

Or see this ["walkthrough"](https://www.youtube.com/embed/H1QZaKXtvO0?si=ladUXTozcgan7jQe).
