# AWS App Runner

## [Getting Started](https://docs.aws.amazon.com/apprunner/latest/dg/getting-started.html)

AWS App Runner service helps developers deploy applications/services to the
cloud based on source code repositories or container images, without the need
to manage the infrastructure hosting the application/service.

Internally, for source code repositories as well, AWS will build a Docker image
for your service, store it in Artifactory and then deploy it. We control the
build and deploy process for our service using configuration files which we can
check into the source code repository itself.

App Runner supports CI/CD integration with the source code, so commits can lead
to services being redeployed. It also provides automatic rollback to the last
working version of the service if the new commit was buggy.

## [Developing For App Runner](https://docs.aws.amazon.com/apprunner/latest/dg/develop.html)

Whether we provide a container image or App Runner builds one for us, App
Runner runs our application code in a container instance. App Runner provides
support for HTTP/1.0 and HTTP/1.1 to the container instances. We don't need to
implement handling of HTTPS secure traffic. App Runner redirects all incoming
HTTP requests to corresponding HTTPS endpoints. We don't need to configure any
settings to enable redirecting the HTTP web requests. App Runner terminates the
TLS before passing requests to our application container instance.
