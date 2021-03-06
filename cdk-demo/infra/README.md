# infra

List all stacks

    npx cdk list

### Steps

1.  Deploy `secrets` stack

    ```
    npx cdk deploy MyOrganizationFoo-CommonSecrets
    ```

2.  [Create a Github personal access token](https://docs.aws.amazon.com/codepipeline/latest/userguide/GitHub-create-personal-token-CLI.html)

3.  Store the token to Secrets Manager existing value

    ```
    aws secretsmanager put-secret-value --secret-id <id> --secret-string <value>
    ```

4.  Deploy the application stacks

    ```
    npx cdk deploy MyOrganizationFoo-MyServerlessApplication-staging
    npx cdk deploy MyOrganizationFoo-MyServerlessApplication-production
    ```

5.  Deploy the pipeline

    ```
    npx cdk deploy MyOrganizationFoo-Pipeline-MyServerlessApplication
    ```
