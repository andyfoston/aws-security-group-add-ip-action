# AWS Security Group Add IP Action

This action will add your public ip address to your given aws security group(s) with a description.
If any ip address already exists with the description then it will update the address instead of adding.
And it will remove the added ip address once the main job is completed.

## Inputs

### `aws-access-key-id`

**Required** AWS Access Key ID.

### `aws-secret-access-key`

**Required** AWS Secret Access Key.

### `aws-region`

**Required** AWS Region.

### `aws-security-group-id`

**Required** AWS Security Group (comma separated if multiple).

### `aws-role-arn`

AWS role ARN (Optional)

### `aws-session-name`

AWS role session name. Required if using an AWS role, otherwise this is ignored.

### `aws-duration-seconds`

The role session duration in seconds. Optional when used with an AWS role, and ignored if not.

### `port`

The port which you want to allow. Default `"22"`.

### `description`

The descriptipn of your IP permission. Default `"GitHub Action"`.

## Example usage
```yaml
- name: Add public IP to AWS security group
  uses: sohelamin/aws-security-group-add-ip-action@master
  with:
    aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
    aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
    aws-region: 'us-east-1'
    aws-security-group-id: ${{ secrets.AWS_SECURITY_GROUP_ID }}
    port: '22'
    description: 'GitHub Action'
```
