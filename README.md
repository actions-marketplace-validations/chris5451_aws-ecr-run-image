# AWS ECR RUN IMAGE Action

This Action allows you to pull docker images from private ECR Repos and run them for your workflow

## Parameters
| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `access_key_id` | `string` | | Your AWS access key id |
| `secret_access_key` | `string` | | Your AWS secret access key |
| `account_id` | `string` | | Your AWS Account ID |
| `repo` | `string` | | Name of your ECR repository |
| `region` | `string` | | Your AWS region |
| `tag` | `string` | | Your image tag |
| `name` | `string` | | Name for the container |
| `port` | `number` | | Port to publish |


## Usage

```yaml
jobs:
  pull-and-run:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - uses: chris5451/aws-ecr-run-image@main
        with:
          access_key_id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          secret_access_key: ${{ secrets.AWS_ACCESS_SECRET_KEY }}
          account_id: ${{ secrets.AWS_ACCOUNT_ID }}
          repo: redis
          region: ${{ secrets.AWS_REGION }}
          tag: latest
          name: Redis
          port: 6379
```

## License
The MIT License (MIT)
