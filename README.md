[![CircleCI](https://circleci.com/gh/Goddhi/Ci-CD-Project.svg?style=svg&circle-token=<YOUR_STATUS_API_TOKEN>)](https://app.circleci.com/pipelines/github/Goddhi/Ci-CD-Project)

<h1>Blue Green Deployment </h1>
- Sets up a complete blue deployment with infrastructure including:<br>
   - Static website deployed in an S3 bucket<br>
   - Cloudfront pointing to the static website<br>
- Creates a green deployment with the following infrastructure:<br>
  - S3 website frontend<br>
  - EC2 backend with NodeJS<br>
  - Postgres Database<br>
  - Integration tests with:<br>
  - Slack integration<br>
  - Frontend and backend smoke testing<br>
 - Sets up centralised structured logging and diagnosis with:<br> 
  - Prometheus for monitoring<br>
  - Gmail for automated notifications<br>


  <h2>Steps</h2>

   - Fork this repository to your local machine
   - connect the repo to circleCI using the link below
   - [Circle CI](www.circleci.com)
   - Create an Environment varaible for AWS access in CircleCI

   - AWS_ACCESS_KEY_ID: Your AWS access key ID
   - AWS_DEFAULT_REGION: Your default AWS region
   - AWS_SECRET_ACCESS_KEY: Your AWS secret key

   <h3>Create an Application Password using Gmail via the link below</h3>

   [Create application password](https://support.google.com/accounts/answer/185833?hl=en)

  - AuthEmail: Authentication email
  - EmailPassword: app password
  - FromEmail: Email to send Prometheus notifications from
  - ToEmail: The email to receive the notifications

    Slack (create a slack app and fill in the following required items to auto-notify your channel on failure)

    - SLACK_ACCESS_TOKEN
    - SLACK_DEFAULT_CHANNEL

    Database parameters for postgres DB
    A sample file is in ./backend/development.env. The only parameter you need to change here is TYPEORM_PASSWORD

      TYPEORM_CONNECTION=postgres
      TYPEORM_DATABASE=postgres
      TYPEORM_ENTITIES=./src/modules/domain/**/*.entity.ts
      TYPEORM_MIGRATIONS=./src/migrations/*.ts
      TYPEORM_MIGRATIONS_DIR=./src/migrations
      TYPEORM_USERNAME=postgres
      TYPEORM_PORT=5432
      TYPEORM_PASSWORD: any password of your choice
### Built With

- [Circle CI](www.circleci.com) - Cloud-based CI/CD service
- [Amazon AWS](https://aws.amazon.com/) - Cloud services
- [AWS CLI](https://aws.amazon.com/cli/) - Command-line tool for AWS
- [CloudFormation](https://aws.amazon.com/cloudformation/) - Infrastrcuture as code
- [Ansible](https://www.ansible.com/) - Configuration management tool
- [Prometheus](https://prometheus.io/) - Monitoring tool

### License

[License](LICENSE.md)
