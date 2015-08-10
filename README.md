# AWS CloudWatch Custom Metrics

You can send custom metrics to AWS CloudWatch like disk/memory usage

## Usage

### Basic usage
1. Create php file like awscw-agent.php

``` php
<?php

use AWSCustomMetric\Sender as CWSender;

try {
// Create the Sender
$cwSender = new CWSender("AWS_KEY", "AWS_SECRET", "AWS_REGION");
$cwSender->setNamespace('Custom/System');
$cwSender->addPlugin(['DiskUsage', 'MemoryUsave']);
$cwSender->run();
} catch (\Exception $e) {
    //Error handling
}

// ...
```

2. Add to cron like :

*/10 * * * * /path/to/php /path/to/awscw-agent.php

## TODO
* NOT TESTED.

## Contributing
You can contribute by forking the repo and creating pull requests. You can also create issues or feature requests.

## Disclaimer
Your AWS CloudWatch usage my be charged. Please check CloudWatch pricing page : https://aws.amazon.com/cloudwatch/pricing/

## License
This project is licensed under the MIT license. `LICENSE` file can be found in this repository.