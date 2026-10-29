# Awesome ECS [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Container orchestration service on AWS that runs containers on Fargate, EC2 or ECS Managed Instances.

A curated list of tools, infrastructure as code, guides and resources for [Amazon Elastic Container Service](https://aws.amazon.com/ecs/) (ECS) and [AWS Fargate](https://aws.amazon.com/fargate/). Only maintained projects are listed. Entries marked *by the list maintainer* come from the people who keep this list.

## Contents

- [Official Resources](#official-resources)
- [Learning](#learning)
- [Desktop and Terminal UIs](#desktop-and-terminal-uis)
- [Command-Line Tools](#command-line-tools)
- [Deployment](#deployment)
- [Infrastructure as Code](#infrastructure-as-code)
- [CI/CD](#cicd)
- [Observability](#observability)
- [Security](#security)
- [Cost](#cost)
- [Online Tools](#online-tools)
- [AI Assistants](#ai-assistants)
- [Runtime and Agents](#runtime-and-agents)

## Official Resources

- [Amazon ECS Developer Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html) - Reference documentation for every ECS concept and feature.
- [Amazon ECS Best Practices Guide](https://docs.aws.amazon.com/AmazonECS/latest/bestpracticesguide/intro.html) - AWS's recommendations for networking, scaling, security, storage and operations.
- [AWS Containers Blog](https://aws.amazon.com/blogs/containers/) - Launch announcements and deep dives from the AWS container teams.
- [AWS Containers Roadmap](https://github.com/aws/containers-roadmap) - Public roadmap for ECS, ECR and Fargate where you can upvote and request features.
- [Task Definition Parameters](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task_definition_parameters.html) - Every field of a task definition, with defaults and launch type support.

### Features Worth Knowing

- [Blue/Green Deployments](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/deployment-type-blue-green.html) - Native blue/green deployments with lifecycle hooks and bake time, without CodeDeploy.
- [Capacity Providers](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/cluster-capacity-providers.html) - How ECS picks and scales the compute that tasks run on.
- [Deployment Circuit Breaker](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/deployment-circuit-breaker.html) - Stops failing rolling deployments and rolls them back automatically.
- [ECS Anywhere](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-anywhere.html) - Runs ECS tasks on your own servers and VMs outside AWS.
- [ECS Exec](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-exec.html) - Interactive shells and one-off commands in running containers through Session Manager.
- [ECS Express Mode](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/express-service-overview.html) - Creates a production-ready web service with load balancer, scaling and TLS from just an image.
- [ECS Gateway](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/gateway-overview.html) - Managed ingress that routes HTTP traffic to ECS services without a load balancer you run yourself.
- [ECS Managed Instances](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ManagedInstances.html) - EC2 capacity that AWS provisions, patches and scales for you.
- [Managed Daemons](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/managed-daemons.html) - Runs one agent per host on ECS Managed Instances.
- [Secrets in Task Definitions](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/specifying-sensitive-data.html) - Injects values from Secrets Manager and Parameter Store as environment variables.
- [Service Connect](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-connect.html) - Service-to-service discovery and traffic with built-in metrics and retries.

## Learning

- [Amazon ECS Immersion Day](https://catalog.workshops.aws/ecs-immersion-day/en-US) - Hands-on AWS workshop from first task to networking, scaling and observability.
- [AWS Builder Center: Containers](https://builder.aws.com/learn/topics/containers) - Patterns, articles and sample code for containers on AWS, the new home of containersonaws.com.
- [Containers from the Couch](https://www.youtube.com/containersfromthecouch) - Video show by AWS container specialists with demos and launch walkthroughs.
- [ECS Solution Blueprints Workshop](https://catalog.workshops.aws/ecs-solution-blueprints/en-US) - Guided walkthrough of the ECS Blueprints for Terraform and CDK.
- [ECS Blue/Green Deployment Patterns](https://github.com/aws-samples/sample-amazon-ecs-blue-green-deployment-patterns) - Sample setups for native blue/green deployments with ALB, NLB and Service Connect.


### Articles
 
- [Accelerate Safe Software Releases with Built-In Blue/Green Deployments](https://aws.amazon.com/blogs/aws/accelerate-safe-software-releases-with-new-built-in-blue-green-deployments-in-amazon-ecs/) - Launch walkthrough of native blue/green deployments with bake time and lifecycle hooks.
- [Amazon ECS at AWS re:Invent 2025](https://aws.amazon.com/blogs/containers/amazon-ecs-at-aws-reinvent-2025/) - Summary of the ECS launches and sessions from re:Invent 2025.
- [Amazon ECS Task Placement](https://aws.amazon.com/blogs/compute/amazon-ecs-task-placement/) - How placement strategies and constraints decide which EC2 instance a task lands on.
- [Announcing Amazon ECS Managed Instances](https://aws.amazon.com/blogs/aws/announcing-amazon-ecs-managed-instances-for-containerized-applications/) - What Managed Instances are and how they sit between Fargate and self-managed EC2.
- [Automate Rollbacks for ECS Rolling Deployments with CloudWatch Alarms](https://aws.amazon.com/blogs/containers/automate-rollbacks-for-amazon-ecs-rolling-deployments-with-cloudwatch-alarms/) - Rolling back deployments on application metrics, not only on failed tasks.
- [Build Production-Ready Applications with Amazon ECS Express Mode](https://aws.amazon.com/blogs/aws/build-production-ready-applications-without-infrastructure-complexity-using-amazon-ecs-express-mode/) - Walkthrough of Express Mode and the resources it creates.
- [Choosing Between ECS Blue/Green Native or AWS CodeDeploy](https://aws.amazon.com/blogs/devops/choosing-between-amazon-ecs-blue-green-native-or-aws-codedeploy-in-aws-cdk/) - Feature comparison and migration path from CodeDeploy to native blue/green, with CDK examples.
- [Deep Dive into Fargate Spot](https://aws.amazon.com/blogs/compute/deep-dive-into-fargate-spot-to-run-your-ecs-tasks-for-up-to-70-less/) - How Fargate Spot capacity providers work and how to handle interruptions.
- [ECS Daemons Explained](https://bayplan.dev/blog/ecs-daemons-explained) - DAEMON services on EC2 compared with Managed Daemons on Managed Instances. 🏠
- [ECS Exec: Open a Shell in a Running Container](https://bayplan.dev/blog/ecs-exec-shell-into-container) - Setting up ECS Exec on Fargate and EC2 and fixing the usual errors. 🏠
- [ECS Native Blue/Green Is Here](https://dev.to/t-kikuc/ecs-native-bluegreen-is-here-with-strong-hooks-and-dark-canary-8ff) - Hands-on test of native blue/green, lifecycle hooks and dark canary traffic, including limitations.
- [EKS vs. ECS: Unexpected Differences](https://www.doit.com/blog/eks-vs-ecs-unexpected-differences-and-practical-advice-on-which-to-use/) - Long comparison of cost, scaling, IaC and maintenance trade-offs between ECS and EKS.
- [Fargate vs EC2 for Amazon ECS](https://bayplan.dev/blog/ecs-fargate-vs-ec2) - Cost, capabilities and effort of Fargate, EC2 and Managed Instances compared. 🏠
- [Graceful Shutdowns with ECS](https://aws.amazon.com/blogs/containers/graceful-shutdowns-with-ecs/) - How SIGTERM, stopTimeout and load balancer draining play together when tasks stop.
- [How ECS Rolling Deployments Work](https://bayplan.dev/blog/ecs-rolling-deployments-explained) - Minimum healthy percent and maximum percent, with an interactive simulator. 🏠
- [How Figma Migrated onto Kubernetes](https://www.figma.com/blog/migrating-onto-kubernetes/) - Why a large ECS user moved to EKS, useful for knowing where ECS falls short.
- [Managing Compute for ECS Clusters with Capacity Providers](https://aws.amazon.com/blogs/containers/managing-compute-for-amazon-ecs-clusters-with-capacity-providers/) - How capacity providers and managed scaling decide when instances start and stop.
- [Migrate from Service Discovery to Service Connect](https://aws.amazon.com/blogs/containers/migrate-existing-amazon-ecs-services-from-service-discovery-to-amazon-ecs-service-connect/) - Step-by-step move of existing services from Cloud Map DNS discovery to Service Connect.
- [Scale to 15,000+ Tasks in a Single ECS Cluster](https://aws.amazon.com/blogs/containers/scale-to-15000-tasks-in-a-single-amazon-elastic-container-service-ecs-cluster/) - Quotas, API rate limits and design choices for very large clusters.
- [The ECS Service Was Healthy. Users Still Got 502s.](https://builder.aws.com/content/3KJhe5gq3r1bKzDBq4ln95m2Db6/the-ecs-service-was-healthy-users-still-got-s) - Aligning ALB draining, SIGTERM handling and app shutdown so deployments drop no requests.
- [What Is Amazon ECS Gateway](https://bayplan.dev/blog/ecs-gateway-explained) - What ECS Gateway creates for each service and the limits to know. 🏠
 


## Desktop and Terminal UIs

- [AWS Toolkit for JetBrains](https://github.com/aws/aws-toolkit-jetbrains) - JetBrains IDE plugin for browsing AWS resources, including ECS clusters and services.
- [AWS Toolkit for VS Code](https://github.com/aws/aws-toolkit-vscode) - VS Code extension with an ECS explorer and [ECS Exec terminals](https://docs.aws.amazon.com/toolkit-for-vscode/latest/userguide/ecs-exec.html).
- [Bayplan](https://bayplan.dev) - Desktop app for clusters, services, tasks, logs, metrics and ECS Exec across AWS accounts and regions. 💰🏠
- [e1s](https://github.com/keidarcy/e1s) - Terminal UI for ECS in the style of k9s, with logs, exec and port forwarding.

## Command-Line Tools

- [ecsgo](https://github.com/tedsmitt/ecsgo) - Interactive prompt that picks a cluster, task and container and opens an ECS Exec session.
- [ecsk](https://github.com/yukiarrr/ecsk) - Interactive wrapper for run-task, execute-command and stop-task, plus file copy to and from containers.
- [ecsrun](https://github.com/masterpointio/ecsrun) - Runs one-off tasks from an existing task definition using a config file.
- [ecsta](https://github.com/fujiwara/ecsta) - Task assistant for listing tasks, exec, port forwarding, file copy and logs.
- [Steampipe AWS Plugin](https://hub.steampipe.io/plugins/turbot/aws/tables/aws_ecs_service) - Query ECS clusters, services and tasks across accounts and regions with SQL.

## Deployment

- [Defang](https://github.com/DefangLabs/defang) - Deploys Docker Compose projects to ECS in your own AWS account.
- [deployfish](https://github.com/caltechads/deployfish) - Manages ECS services, tasks and their config from a single YAML file.
- [ecs-deploy](https://github.com/fabfuel/ecs-deploy) - CLI for redeploying services with a new image, rolling back, scaling and running tasks.
- [ecs-deploy (in4it)](https://github.com/in4it/ecs-deploy) - Self-hosted deployment platform for ECS with a web UI and JSON service definitions.
- [ECS ComposeX](https://github.com/compose-x/ecs_composex) - Turns Docker Compose files with AWS extensions into CloudFormation for ECS.
- [ecs-tool](https://github.com/springload/ecs-tool) - Deploys services and runs one-off commands with live log output.
- [ecschedule](https://github.com/Songmu/ecschedule) - Manages ECS scheduled tasks as code.
- [ecspresso](https://github.com/kayac/ecspresso) - Deploys services from plain task and service definition files, with diff, verify and rollback.
- [Flightcontrol](https://www.flightcontrol.dev/) - Platform that deploys apps to ECS and other AWS services in your own account. Commercial.

## Infrastructure as Code

- [AWS CDK ECS Module](https://docs.aws.amazon.com/cdk/api/v2/docs/aws-cdk-lib.aws_ecs-readme.html) - Constructs for clusters, task definitions and services.
- [AWS CDK ECS Patterns](https://docs.aws.amazon.com/cdk/api/v2/docs/aws-cdk-lib.aws_ecs_patterns-readme.html) - Higher-level constructs such as load-balanced and queue-processing Fargate services.
- [AWS CDK Examples](https://github.com/aws-samples/aws-cdk-examples) - Sample CDK apps in several languages, many of them for ECS and Fargate.
- [AWS CloudFormation Templates](https://github.com/aws-cloudformation/aws-cloudformation-templates) - Official sample templates, including ECS clusters and services.
- [CDK ECS Service Extensions](https://github.com/cdklabs/cdk-ecs-service-extensions) - Adds sidecars and integrations to CDK ECS services as pluggable extensions.
- [Cloud Posse ECS Modules](https://github.com/cloudposse/terraform-aws-ecs-alb-service-task) - Terraform modules for ALB services, [container definitions](https://github.com/cloudposse/terraform-aws-ecs-container-definition) and [clusters](https://github.com/cloudposse/terraform-aws-ecs-cluster).
- [ECS Blueprints](https://github.com/aws-ia/ecs-blueprints) - Complete ECS solutions as Terraform and CDK examples from AWS.
- [Pulumi AWSx](https://github.com/pulumi/pulumi-awsx) - Pulumi components for Fargate and EC2 services with sensible defaults.
- [SST](https://github.com/anomalyco/sst) - Framework whose [Service component](https://sst.dev/docs/component/aws/service/) runs containers on ECS Fargate.
- [Terraform AWS ECS Module](https://github.com/terraform-aws-modules/terraform-aws-ecs) - Community Terraform module for clusters, services and capacity providers.

## CI/CD

- [Amazon ECR Login Action](https://github.com/aws-actions/amazon-ecr-login) - GitHub Action that logs Docker into Amazon ECR.
- [Amazon ECS Deploy Express Service Action](https://github.com/aws-actions/amazon-ecs-deploy-express-service) - GitHub Action that deploys an ECS Express Mode service.
- [Amazon ECS Deploy Task Definition Action](https://github.com/aws-actions/amazon-ecs-deploy-task-definition) - GitHub Action that registers a task definition and deploys it to a service.
- [Amazon ECS Render Task Definition Action](https://github.com/aws-actions/amazon-ecs-render-task-definition) - GitHub Action that inserts a new image URI into a task definition file.
- [AWS ECS Orb](https://github.com/CircleCI-Public/aws-ecs-orb) - CircleCI orb for updating ECS services and running tasks.
- [Cloud Posse ECS CodePipeline](https://github.com/cloudposse/terraform-aws-ecs-codepipeline) - Terraform module for a CodePipeline and CodeBuild pipeline that deploys to ECS.
- [Configure AWS Credentials Action](https://github.com/aws-actions/configure-aws-credentials) - GitHub Action for short-lived AWS credentials through OIDC.

## Observability

- [AWS Distro for OpenTelemetry Collector](https://github.com/aws-observability/aws-otel-collector) - AWS-supported OpenTelemetry Collector that runs as an ECS sidecar or daemon.
- [AWS for Fluent Bit](https://github.com/aws/aws-for-fluent-bit) - Fluent Bit image used by FireLens to route container logs.
- [CloudWatch Container Insights](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/cloudwatch-container-insights.html) - Cluster, service and task metrics in CloudWatch.
- [ecs_exporter](https://github.com/prometheus-community/ecs_exporter) - Prometheus exporter for task metadata and container stats.
- [FireLens Examples](https://github.com/aws-samples/amazon-ecs-firelens-examples) - Sample FireLens configurations for sending logs to many destinations.

## Security

- [Amazon ECS Exec Checker](https://github.com/aws-containers/amazon-ecs-exec-checker) - Script that checks whether a task is set up correctly for ECS Exec.
- [chamber](https://github.com/segmentio/chamber) - CLI for storing secrets in Parameter Store and loading them into processes.
- [Checkov](https://github.com/bridgecrewio/checkov) - Static analysis for IaC with checks for ECS task definitions and services.
- [Prowler](https://github.com/prowler-cloud/prowler) - Cloud security scanner with checks for ECS configuration.
- [Trivy](https://github.com/aquasecurity/trivy) - Scanner for vulnerabilities and misconfigurations in images and IaC.

## Cost

- [AWS Compute Optimizer for ECS](https://docs.aws.amazon.com/compute-optimizer/latest/ug/view-ecs-recommendations.html) - CPU and memory recommendations for Fargate services.
- [Fargate Pricing](https://aws.amazon.com/fargate/pricing/) - Official per-vCPU and per-GB prices, including Spot.
- [Infracost](https://github.com/infracost/infracost) - Cost estimates for Terraform changes in pull requests.

## Online Tools

- [AWS Pricing Calculator](https://calculator.aws/) - Official calculator for ECS, Fargate and EC2 estimates.
- [ECS Cost Calculator](https://bayplan.dev/tools/ecs-cost-calculator) - Compares the monthly cost of a set of services on Fargate and EC2, with Spot and Savings Plans. 🏠
- [ECS EC2 Instance Finder](https://bayplan.dev/tools/ecs-ec2-instance-finder) - Finds the cheapest EC2 instance types for a set of ECS services. 🏠
- [ECS IAM Policy Generator](https://bayplan.dev/tools/ecs-iam-policy-generator) - Least-privilege task, task execution and container instance policies as JSON or Terraform. 🏠

## AI Assistants

- [Amazon ECS MCP Server](https://github.com/awslabs/mcp/tree/main/src/ecs-mcp-server) - MCP server that lets AI assistants deploy, inspect and troubleshoot ECS, also available [fully managed](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-mcp-introduction.html).

## Runtime and Agents

- [Amazon ECS Agent](https://github.com/aws/amazon-ecs-agent) - Agent that connects EC2 and external instances to ECS and runs their tasks.
- [Amazon ECS-Optimized AMI](https://github.com/aws/amazon-ecs-ami) - Packer recipes behind the official ECS-optimized Amazon Linux AMIs.
- [Amazon ECS Local Container Endpoints](https://github.com/awslabs/amazon-ecs-local-container-endpoints) - Local versions of the task metadata and task IAM role endpoints for development.
- [Bottlerocket](https://github.com/bottlerocket-os/bottlerocket) - Minimal, container-focused Linux with ECS variants.
- [Service Connect Agent](https://github.com/aws/amazon-ecs-service-connect-agent) - Envoy-based proxy behind ECS Service Connect.

## Related Lists

- [Awesome AWS](https://github.com/donnemartin/awesome-aws#readme) - Libraries, tools and resources across all of AWS.
- [Awesome Docker](https://github.com/veggiemonk/awesome-docker#readme) - Docker resources and projects.
- [awesome-ecs](https://github.com/nathanpeck/awesome-ecs#readme) - Alternative Awesome ECS list.

💰 - paid product or service
🏠 - made by the maintainers of this list

## Contributing

Contributions are welcome. Read the [contribution guidelines](contributing.md) first.
