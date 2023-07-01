# Online Raffle System

This project is a demonstration of an online raffle system developed using Vaadin Flow, Docker, Traefik, Terraform, and Ansible. It provides a platform where users can create, manage, and participate in raffles securely and at scale.

## Features

- [ ] User registration via OAuth2 authentication or self-registration.
- [ ] Editable user profile with personal information and password change.
- [ ] Event creation with configurable collaborators and permissions.
- [ ] Participant management through manual entry or import from CSV file.
- [ ] Personalized dashboard displaying subscribed events for the user.
- [ ] Ability to reuse participant lists from previous events.
- [ ] Raffle generation with specification of prizes and available ticket quantity.
- [ ] Raffle ticket sales and payment management.
- [ ] Public links for sharing raffles.

## System Requirements

- Java 17 or higher.
- Vaadin 24
- Spring Boot 3
- Maven 3.x.
- Docker and Docker Compose.
- Traefik
- Terraform.
- Ansible.

## Project structure

- `MainLayout.java` in `src/main/java` contains the navigation setup (i.e., the
  side/top bar and the main menu). This setup uses
  [App Layout](https://vaadin.com/docs/components/app-layout).
- `views` package in `src/main/java` contains the server-side Java views of your application.
- `views` folder in `frontend/` contains the client-side JavaScript views of your application.
- `themes` folder in `frontend/` contains the custom CSS styles.


## Deployment

### Instant Server deployment

To deploy the Online Raffle System, follow these steps:

1. Clone the repository

```
git clone https://github.com/fredpena/raffle
docker-compose up 
```

2. Running the application

The project is a standard Maven project. To run it from the command line,
type `mvnw` (Windows), or `./mvnw` (Mac & Linux), then open
`http://localhost:8080` in your browser.

### Deploying to Production

To create a production build, call `mvnw clean package -Pproduction` (Windows),
or `./mvnw clean package -Pproduction` (Mac & Linux).
This will build a JAR file with all the dependencies and front-end resources,
ready to be deployed. The file can be found in the `target` folder after the build completes.

Once the JAR file is built, you can run it using
`java -jar target/raffle.jar`

### Deploying using Docker

To build the Dockerized version of the project, run

```
mvn clean package -Pproduction
docker build -t raffle:latest .
docker buildx build --platform=linux/amd64 -o type=docker -t raffle:latest . 
```

Once the Docker image is correctly built, you can test it locally using

```
docker run -p 8080:8080 raffle:latest
```

### To make the infrastructure and deploy the application on the provisioned infrastructure

- Use Terraform to provision the necessary infrastructure resources.
- Use Ansible to configure and deploy the application on the provisioned infrastructure. 

For detailed deployment instructions and customization options, please refer to the [Deployment Guide](deployment.md).

## Contributing

If you'd like to contribute to this project, follow these steps:

1. Fork this repository.
2. Create a new branch for your feature or enhancement: `git checkout -b branch-name`.
3. Make your changes and commit them: `git commit -m "Description of changes"`.
4. Push your changes to the remote repository: `git push origin branch-name`.
5. Open a pull request on GitHub.

## License

<!--- This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).-->

## Contact

If you have any questions or suggestions, you can contact the development team via [email](mailto:me@fredpena.dev).

