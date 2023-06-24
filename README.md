# Redis cluster cache storage plugin for CakePHP

This is a fork of the [kgbph/cakephp-redis-cluster](https://github.com/kgbph/cakephp-redis-cluster). This fork only changes the namespacing of the plugin and the minimum required php version.

## Installation

You can install this plugin into your CakePHP application using [composer](https://getcomposer.org).

The recommended way to install composer packages is:

```
composer require zunnu/cake-redis-cluster
```

## Usage

Use as a cache engine. See [CakePHP Caching](https://book.cakephp.org/3/en/core-libraries/caching.html).

``` php
Cache::setConfig('redis', [
    'className' => 'CakeRedisCluster.RedisCluster',
    'nodes' => [
        'redis-node-0:6379',
        'redis-node-1:6379',
        'redis-node-2:6379',
        'redis-node-3:6379',
        'redis-node-4:6379',
        'redis-node-5:6379',
    ],
]);
```

## Options
| Name         | Type           | default | Description                          |
|--------------|----------------|---------|--------------------------------------|
| duration     | int            | 3600    | Specify how long items last          |
| failover     | string \| null | null    | Automatic slave failover mode        |
| groups       | string[]       | []      | List of associated groups or 'tags'  |
| name         | string \| null | null    | Redis cluster name                   |
| nodes        | string[]       | []      | URL or IP of the Redis cluster nodes |
| persistent   | bool           | true    | Use persistent connection            |
| prefix       | string         | 'cake_' | Prefix prepended to all entries      |
| read_timeout | float          | 0       | Read timeout in seconds              |
| timeout      | float          | 0       | Timeout in seconds                   |

---

## Code quality checks

### PHP CodeSniffer
Execute `composer cs-check` inside the PHP container.

### PHP Static Analysis Tool
Execute `composer stan` inside the PHP container.

### PHPUnit
Execute `composer test` inside the PHP container.

### Run all checks
Execute `composer check` inside the PHP container.
