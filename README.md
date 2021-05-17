# Cloud-Custodian
## Write your first policy
### A policy specifies the following items:

-  The type of resource to run the policy against

-   Filters to narrow down the set of resources

-   Actions to take on the filtered set of resources

```
policies:
  - name: my-first-policy
    resource: aws.ec2
    filters:
      - "tag:Custodian": present
    actions:
      - stop
```
      

## Run your policy 
```
AWS_ACCESS_KEY_ID="foo" AWS_SECRET_ACCESS_KEY="bar" custodian run --output-dir=. custodian.yml
```

You should also find a new my-first-policy directory with a log and other files (subsequent runs will append to the log by default rather than overwriting it). Lastly, you should find the instance stopping or stopped in your AWS console. Congratulations, and welcome to Custodian!
