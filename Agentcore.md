Doesn't IAM include the roles and manages policy etc, why didn't you add descriptions over it? Shouldn't it be on a  security review

You are absolutely right. IAM Roles, Trust Policies, and Permissions Policies are the foundational elements of AWS security, and a proper security review document must explicitly define and audit them. 

Here is the detailed IAM breakdown, complete with descriptions and specific review items for your AWS Bedrock AgentCore security document:

## 1. IAM Roles (Execution and Service Roles)
*Description:* Bedrock AgentCore relies on distinct IAM roles to separate the permissions of the calling application from the agent's runtime environment. This limits the blast radius if an application is compromised.
*Review Items:*
- **Role Separation:** Ensure distinct roles are created for different components. Specifically, verify the separation between the *AgentCore Runtime Execution Role* (which the agent uses to run and access models) and the *Gateway Execution Role* (used to evaluate Cedar policies and invoke targets) [1][2].
- **Caller vs. Agent Privilege:** Confirm that the application or user invoking the agent does not share the same IAM role as the agent itself [2]. The caller only needs `bedrock-agentcore:InvokeAgentRuntime`, while the agent needs backend execution permissions [3].

## 2. Trust Policies (AssumeRole Configurations)
*Description:* Trust policies (Resource-based policies attached to IAM roles) dictate exactly which AWS services or identities are allowed to assume your Bedrock AgentCore roles.
*Review Items:*
- **Service Principal Restriction:** Confirm that the trust policy's `Principal` block strictly limits assumption to the Bedrock AgentCore service (`bedrock-agentcore.amazonaws.com`) [1].
- **Confused Deputy Prevention:** Verify that every `sts:AssumeRole` statement includes explicit `Condition` keys for `aws:SourceAccount` (matching your AWS Account ID) and `aws:SourceArn` (matching the specific AgentCore resource ARN) [1]. This prevents other AWS accounts from using your agent's role.

## 3. Permissions Policies (Managed vs. Custom)
*Description:* Identity-based policies define the exact actions the Bedrock AgentCore roles can perform on specific AWS resources. 
*Review Items:*
- **Audit AWS Managed Policies:** Check for overly broad AWS managed policies like `BedrockAgentCoreFullAccess` or `AmazonBedrockFullAccess` [4][5]. Flag these for removal in production environments, as they violate the principle of least privilege.
- **Custom Least-Privilege Policies:** Ensure broad policies are replaced with scoped Customer Managed Policies or Inline Policies. For example, CloudWatch logging permissions should be restricted strictly to `/aws/bedrock-agentcore/runtimes/*` and `/aws/bedrock-agentcore/evaluations/*` log groups rather than allowing wildcard logging [2][6].
- **Downstream Resource Scoping:** Audit the policy to ensure it explicitly whitelists only the exact KMS keys, Lambda functions, Secrets Manager secrets, or S3 buckets the agent needs to execute its specific tools [6][7]. 

## 4. Resource-Based Policies
*Description:* Policies attached directly to the Bedrock AgentCore resources (such as the Runtime or Gateway) that dictate who can access them from the outside.
*Review Items:*
- **Network Perimeter Enforcement:** Verify that resource-based policies are configured to deny `bedrock-agentcore:InvokeAgentRuntime` requests that do not originate from your authorized Amazon VPC (using the `aws:SourceVpc` condition key) [3].
- **Principal Allow-listing:** Ensure the resource policy only grants invocation rights to specific, approved application identities or organizational units, explicitly denying public or cross-account access unless strictly required [2][3].

## 5. Permissions Boundaries
*Description:* An advanced IAM feature used to set the maximum permissions that an identity-based policy can grant to an agent's role, acting as a failsafe against misconfiguration.
*Review Items:*
- **Boundary Implementation:** Ensure a permissions boundary is attached to all AgentCore execution roles. This guarantees that even if a developer accidentally attaches `AdministratorAccess` to the agent's inline policy, the boundary will block the agent from performing unauthorized actions outside of its designated sandbox.

Would you like to move on to the network security or data encryption sections of the review document next?


