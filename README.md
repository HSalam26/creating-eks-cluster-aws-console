# Creating an Amazon EKS Cluster on AWS

This README provides step-by-step instructions on how to create an Amazon Elastic Kubernetes Service (EKS) cluster on AWS. Follow these steps to set up your EKS environment.

## Prerequisites

Before you begin, make sure you have the following prerequisites:

- AWS account with appropriate permissions.
- AWS Command Line Interface (CLI) installed and configured.
- `kubectl` (Kubernetes command-line tool) installed.

## Step-by-Step Guide

1. **Create an EKS Cluster**
   - Use the AWS Management Console or CLI to create an EKS cluster.

2. **Create an IAM Role for the EKS Cluster**
   - Name and create an IAM (Identity and Access Management) role for your EKS cluster with the necessary permissions.

3. **Install and Configure AWS CLI**
   - Install and configure the AWS CLI on your local machine to interact with AWS services.

4. **Install kubectl**
   - Install `kubectl`, the Kubernetes command-line tool, on your local machine.

5. **Check EKS Cluster Status**
   - Run the following command in your IDE to check the status of your EKS cluster:
     ```
     aws eks --region [region] describe-cluster --name [cluster name] --query cluster.status
     ```

6. **Update kubeconfig File**
   - Update the kubeconfig file for your EKS cluster:
     ```
     aws eks --region [region] update-kubeconfig --name [cluster name]
     ```

7. **Verify EKS Connection**
   - Check if your EKS cluster is connected to the master node using:
     ```
     kubectl get svc
     ```

8. **Add Compute Nodes**
   - In the EKS console, navigate to the "Compute" tab and add a node group.

9. **Name the Node Group**

10. **Create an IAM Role for EKS Nodes**
    - Create an IAM role for the EKS nodes with policies such as "AmazonEC2ContainerRegistryReadOnly," "AmazonEKS_CNI_Policy," and "AmazonEKSWorkerNodePolicy."

11. **Choose Instance Type**
    - Select the desired instance type for your EKS nodes (e.g., t3.micro).

12. **Set Disk Size**
    - Specify the disk size for the nodes (e.g., 5 GB).

13. **Enable Remote Access to Nodes**
    - Ensure that remote access to the nodes is enabled for debugging and maintenance.

14. **Monitor Node Creation**
    - Run the following command to monitor the creation of nodes:
      ```
      kubectl get nodes --watch
      ```

15. **Delete Worker Nodes**
    - If needed, delete the worker nodes when you're done with your cluster.

16. **Delete the EKS Cluster**
    - Finally, delete the EKS cluster when you no longer require it.

That's it! You have successfully created an Amazon EKS cluster on AWS and configured it for use with Kubernetes.
