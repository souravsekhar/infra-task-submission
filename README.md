# infra-task-submission
This repo will guide you through the solution for the actual task

Few points to note:

1. This is not a working solution, rather a skeleton structure to address the intent of the task

2. The code has not been deployed to a cloud solution.

3. Code is not tested in a cloud environment, considering the costs involved.

## Repositories

[hello-world](https://github.com/souravsekhar/hello-world) : A simple go app that will be used as a microservice container deployment to K8s

[jenkins](https://github.com/souravsekhar/jenkins-on-ec2): A jenkins server hosted on EC2 instance to be used for CI/CD. Created using terraform.

[eks-cluster](https://github.com/souravsekhar/eks-aws): An EKS cluster to be used as orchestration platform, created using terraform.

[charts](https://github.com/souravsekhar/helm-cd): All required helm charts to deploy the applications on K8s

[charts/hello-world](https://github.com/souravsekhar/helm-cd/tree/master/hello-world): Packaged hello-world app

[charts/prometheus](https://github.com/souravsekhar/helm-cd/tree/master/prometheus): Packaged prometheus for monitoring

[charts/grafana](https://github.com/souravsekhar/helm-cd/tree/master/grafana): Packaged grafana for dashboarding

[automate-deploy](https://github.com/souravsekhar/helm-cd/blob/master/playbook.yaml): ansible playbook to automate the helm deployments.

## Design

Jenkins is used for CI, both for running terraform code to provision infrastructure on AWS, as well as to deploy helm charts on to EKS.

Helm is used for CD to deploy any microservice on the EKS cluster

Terraform is used to provision Jenkins and EKS cluster

Prometheus is used as a metric collector from the microservices.

Grafana is used for visualising the metrics from prometheus.

## Steps

1. Install Jenkins on EC2
2. Configure and run Jenkins jobs for below:-

    1. Create EKS
    2. Destroy EKS (Optional, when needed)
    3. Build app image and push to registry
    4. Execute playbook to deploy K8s resources.


