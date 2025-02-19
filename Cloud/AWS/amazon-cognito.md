# Amazon Cognito overview

Amazon Cognito provides authentication, authorization, and user management for customer's web and mobile applications. Users can sign in directly with a user name and password, or through a third party such as Facebook, Amazon, Google, Apple, or enterprise identity providers via SAML 2.0 and OpenID Connect.

The two main components of Amazon Cognito are `user pools` and `identity pools`. `User pools` are user directories that provide sign-up and sign-in options for application users. `Identity pools` enable developers to grant users access to other AWS services.

{% embed url="https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html" %}

## How does Amazon Cognito work?

![](img/scenario-cup-cib2.png)

1. An user signs in through a `user pool` and receives user pool tokens (JWT tokens) after a successful authentication.
2. An application exchanges the user pool tokens for AWS credentials through an `identity pool`.
3. The user can use the AWS credentials to access other AWS services such as Amazon S3 or DynamoDB.

# Security issues

## Leakage identity pool ID

Identity pool ID allows you to fetch temporary AWS credentials that may have extra AWS permissions. As a result, it may be possible to get unauthenticated access to sensitive AWS services.

Identity pool IDs can be stored client-side, for example within JavaScript, or returned in a response.

{% embed url="https://blog.appsecco.com/exploiting-weak-configurations-in-amazon-cognito-in-aws-471ce761963" %}

# References

- [Whitepaper: Internet-Scale analysis of AWS Cognito Security](https://andresriancho.com/wp-content/uploads/2019/06/whitepaper-internet-scale-analysis-of-aws-cognito-security.pdf)
