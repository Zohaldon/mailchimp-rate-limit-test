# Mailchimp Rate Limit Test

This document provides instructions for conducting a rate limit test on the Mailchimp API using [Artillery](https://artillery.io/). The test is designed to evaluate the performance and reliability of your Mailchimp integration while adhering to rate limits imposed by the Mailchimp API.

## Usage

To perform this test, follow the steps below.

### 1. Install Dependencies

Make sure you have Artillery installed. If not, run the following command to install it:

```shell
npm install -g artillery
```

### 2. Run the Load Test

Use the following commands to initiate and run the rate limit test:

#### Start the Load Test

This command will run the load test and generate a report in `report.json`:

```shell
artillery run -o report.json rate_limit.yml
```

#### Debug the Load Test

If you encounter issues during the test and need detailed HTTP response information for debugging, use the following command:

```shell
DEBUG=http:response artillery run -o report.json rate_limit.yml 2>&1 | tee result.log
```

### 3. Visualize the Report

After running the load test, you can visualize the results using Artillery's built-in reporting functionality. Execute the following command:

```shell
artillery report report.json
```

This will generate HTML reports containing detailed statistics and charts to help you understand the test's performance.

Please ensure you've configured the `rate_limit.yml` file with the appropriate Mailchimp API endpoint and any required authentication tokens before running the test.

## Note

- Respect Mailchimp's rate limits and terms of use during the test to avoid any adverse impact on your integration.
- Exercise caution during the test to prevent any excessive load that could impact the Mailchimp API's performance, potentially leading to rate limiting or account suspension.

Conduct this test responsibly and within the boundaries of Mailchimp's guidelines.
