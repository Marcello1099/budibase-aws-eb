# Budibase AWS Elastic Beanstalk Deployment

This documentation provides detailed instructions on deploying Budibase, an open-source low-code platform, on AWS Elastic Beanstalk (EB), utilizing Amazon Elastic File System (EFS) for persistent storage. This setup is ideal for scalable, resilient, and easy-to-manage Budibase applications.

## Prerequisites

Before proceeding, ensure you have:
- An AWS account with adequate permissions.
- Basic familiarity with EB and EFS.
- The AWS CLI installed and configured on your machine.

## Deployment Steps

### Step 1: Create an EFS

1. Navigate to the EFS console in AWS.
2. Click on "Create file system."
3. Follow the wizard to configure the file system settings. Ensure it is accessible from your VPC.

### Step 2: Configure EB and EFS in Your VPC

1. Create a new EB environment or use an existing one.
2. Ensure that your EB environment and the EFS are in the same VPC.
3. Modify the security groups as necessary to allow communication between EB instances and the EFS.

### Step 3: Configure EFS in the EB Environment

1. Navigate to the `.ebextensions` directory in your project.
2. Open `storage-efs-mountfilesystem.config`.
3. Replace the placeholder with your EFS ID.

### Step 4: Set Budibase Version in Dockerrun File

1. Open `Dockerrun.aws.json` in your project directory.
2. Replace the version placeholder and specify the desired Budibase Docker image version.

### Step 5: Zip and Deploy Budibase Configuration

1. Zip the contents of your Budibase project directory, including the .ebextensions folder.
2. Use the EB console or the AWS CLI to upload and deploy this zip file to your environment.

## Conclusion

Following these steps will successfully deploy Budibase on AWS Elastic Beanstalk with an Amazon Elastic File System, providing a scalable, resilient, and easy-to-manage setup. For further customization and troubleshooting, consult AWS documentation and Budibase community forums.

## Notice

Please ensure that all configurations and commands are double-checked for accuracy before implementation, as specifics may vary based on your AWS setup and Budibase version.


