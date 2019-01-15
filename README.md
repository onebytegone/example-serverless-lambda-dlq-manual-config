# Example: Manually configuring SNS/SQS DLQ for Lambda using Serverless

This is an example of the [failing test case][serverless-3609-sqs-issue] that appears to
have caused Serverless to drop support for SQS DLQs in
[`onError`][serverless-docs-onerror]. The code contained in this example is based on the
following:

   * https://github.com/serverless/serverless/pull/3609#issuecomment-302059073
   * https://github.com/serverless/serverless/pull/3609#issuecomment-341847119
   * https://github.com/serverless/serverless/issues/4647

Please see the individual commits for the various states.

[serverless-3609-sqs-issue]: https://github.com/serverless/serverless/pull/3609#issuecomment-302059073
[serverless-docs-onerror]: https://serverless.com/framework/docs/providers/aws/guide/functions/#dead-letter-queue-dlq

## Deployment

```
git clone git@github.com:onebytegone/example-serverless-lambda-dlq-manual-config.git
cd example-serverless-lambda-dlq-manual-config
git checkout initial_stack_setup
serverless deploy --account-number "${AWS_ACCOUNT_NUMBER}"
git checkout use_sns_dlq_via_arn
serverless deploy --account-number "${AWS_ACCOUNT_NUMBER}"
git checkout use_sqs_dlq_via_arn
serverless deploy --account-number "${AWS_ACCOUNT_NUMBER}"
git checkout use_sns_dlq_via_ref
serverless deploy --account-number "${AWS_ACCOUNT_NUMBER}"
git checkout use_sqs_dlq_via_fnatt
serverless deploy --account-number "${AWS_ACCOUNT_NUMBER}"
```
