
# Cloud Security with AWS IAM  (Identity and Access Management)

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-security-iam)

**Author:** Albert  
**Email:** tapcyberx@gmail.com

---

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/aws-security-iam_1c864649)

---

## Introducing today's project!

### What is AWS IAM?

AWS IAM (Identity and Access Management) service that controls access to AWS resources. It is useful for managing users, roles, and permissions, ensuring secure and granular access control across an AWS environment.










### How I'm using AWS IAM in this project

I used AWS IAM to create and manage users, roles, and policies, ensuring controlled access to AWS resources. Specifically, I assigned permissions to restrict actions on EC2 instances based on environment tags.










### One thing I didn't expect...

I didn’t expect to encounter so many permission restrictions, which highlighted the importance of properly configuring IAM policies for secure and efficient access management.

### This project took me...

it took me around 1.30 H.

---

## Tags

Tags are labels assigned to AWS resources to help users organize, manage, and track them efficiently. They are useful for grouping resources, enabling cost allocation, simplifying automation, and enforcing security policies.

I assigned the Env tag to my EC2 instances, with values Production and Development, representing the two environments used for building and releasing the NextWork App, ensuring better resource organization and management.

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/aws-security-iam_2e0e5a5d)

---

## IAM Policies

It's all about giving permissions to IAM users, groups, or roles, saying what they can or can't do on certain resources.

### The policy I set up

For this project, I’ve set up a policy using JSON editor.

My policy grants all EC2-related actions to instances tagged as "Development" under the Env tag while restricting the ability to create or delete tags on any EC2 instance, ensuring controlled resource management.

### When creating a JSON policy, you have to define its Effect, Action and Resource.

In a JSON policy, Effect defines whether the action is Allowed or Denied. Action specifies the AWS operation being controlled. Resource identifies the specific AWS resource(s) the policy applies to within the account.

---

## My JSON Policy

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/aws-security-iam_1c864649)

---

## Account Alias

An Account Alias is a custom name assigned to an AWS account, replacing the Account ID in the login URL, making it easier to remember and access the account securely.

Creating an account alias took me less than a couple minutes. Simple!
Now, my new AWS console sign-in URL is https://nextwork-alias-albert.signin.aws.amazon.com/console

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/aws-security-iam_0eb4439b)

---

## IAM Users and User Groups

### Users

IAM users are individual identities created in AWS IAM to access an AWS account. They are assigned specific permissions to interact with resources and services based on defined policies.

### User Groups

IAM user groups are useful for grouping and managing user's permmissions at a group level. They at similarly to folders when it come to assigning permission/policies.

I attached the policy I created to this user group, which means all user that are added to that user group will automatically inherit the user group's acess permissions.

---

## Logging in as an IAM User

The first wasy is emailing sign-instructions; and second downloading a csv files.

Once I logged in, I noticed that a lot panels displayed "Access denied". This was a clear difference to the dashboard I usually see in my AWS Account.

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/aws-security-iam_6f2ab446)

---

## Testing IAM Policies

I tested my JSON IAM policy by tryong to stop the development and the production instances i.e triggering the Stop Instances action.

### Stopping the production instance

When I tried to stop the Production instance, I received an error message stating that I was not authorized, preventing me from stopping it due to the applied IAM policy restrictions.

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/aws-security-iam_0e7a9d6a)

---

## Testing IAM Policies

### Stopping the development instance

Next, when I tried to stop the development instance could be stopped. Because the Policy I created (and attached to the user Group taht my User is a part os) allowed all EC2 related actions to all EC2 instances/resources with the Env tag development.

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/aws-security-iam_1811801c)

---

## The IAM Policy Simulator

### How I used the simulator

---

---
