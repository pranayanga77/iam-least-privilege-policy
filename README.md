Role Focus: Cloud Support / Entry-Level Cloud Engineer

# IAM Least Privilege Policy – EC2 Read Only

## Objective
Create a custom IAM policy that follows the **principle of least privilege** by allowing only read-only access to EC2 resources.

---

## What is Least Privilege?
Least privilege means **granting only the minimum permissions required** to perform a task and nothing more.

This helps to:
- Reduce security risks
- Prevent accidental changes
- Limit damage in case of credential compromise

---

## Policy Explanation
This policy allows only EC2 **read-only** actions using:
- `ec2:Describe*`

It does NOT allow:
- Creating instances
- Stopping or terminating instances
- Modifying EC2 configurations

---

## Why `Describe*` is Safer Than `*`
- `Describe*` → Read-only access (safe)
- `*` → Full access (dangerous)

Using `Describe*` ensures the user can **view EC2 resources without modifying them**.

---

## Real-World Use Case
This policy is commonly used for:
- Cloud Support Engineers
- Monitoring teams
- Auditors
- Trainees learning AWS

Users can troubleshoot and analyze EC2 issues **without the risk of making changes**.

---

## How It Was Used
This policy was attached to an IAM group and tested by logging in as an IAM user to verify that:
- EC2 details are visible
- No write or delete actions are allowed

---

## AWS Best Practice
- Avoid using AWS managed policies with excessive permissions
- Use custom policies to enforce least privilege
- Regularly review and audit IAM permissions

