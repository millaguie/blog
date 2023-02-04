---
title: "Terraform Operations"
date: 2023-01-30T15:54:43+01:00
draft: true
---

# Terraform operations

When IaC becomes dirty.

Terraform is a powerful tool that can be used to manage infrastructure as code (IaC). However, as Terraform projects become more complex, it can be easy to get into a situation where you have to operate using terraform, this will make you feel dirty, but sometimes shit happends. In this article, we will discuss some common issues you may need to address when working with Terraform, and some techniques to help you feel less dirty, or at least see that others are facing the same issues.


## Managing Terraform State:

One of the most important aspects of using Terraform is managing your state. Your Terraform state is a representation of your infrastructure, and it is important to keep it up-to-date and in sync with your actual infrastructure. However, as your infrastructure evolves, it can be easy to get into a situation where your state is no longer accurate. There are a few common issues that can cause this, including:

State corruption: This can occur when Terraform writes to your state file while it is being updated, which can result in inconsistent state data. To resolve this issue, you can run the terraform state push command to force a write of your current state to the state file.

Out-of-date state: If you are making changes to your infrastructure outside of Terraform, it is important to make sure your state is updated accordingly. You can run the terraform state pull command to retrieve the latest state from your infrastructure and update your local state file.

Adding and Removing Elements from the State:

Another common issue you may encounter when managing Terraform state is the need to add or remove elements from your state. For example, you may need to add a new resource to your infrastructure, or remove a resource that is no longer needed. To add a new resource to your state, you can run the terraform import command, which allows you to import an existing resource into your Terraform state. To remove a resource from your state, you can run the terraform state rm command, which will remove the resource from your state file.

Unblocking the State:

At times, you may encounter a situation where your state is locked, and you are unable to make changes to your infrastructure. This can occur when multiple users are trying to make changes to the same state at the same time. To resolve this issue, you can run the terraform force-unlock command, which will force the lock to be released, allowing you to make changes to your infrastructure.

In conclusion, Terraform is a powerful tool for managing infrastructure as code. However, it is important to have a solid understanding of how to manage your Terraform state, and how to unblock it when necessary. By following these techniques, you can manage your infrastructure more effectively and avoid common issues that can arise when working with Terraform.

## Related readings

If you want to go deeper in Terraform I recomend the following readings:

* [Terraform in lyz-code's blue book](https://lyz-code.github.io/blue-book/terraform/), for a brief introduction to Terraform.
* [Terraform up and running](https://www.terraformupandrunning.com/), for professional use of terraform.