# laravel-scheduledaemon

Provides a single artisan command to run `schedule:run` as a daemon. Use this if, and only if you can guarantee that all your `schedule:run` executions will terminate in 60 seconds or less. This should be easy if you use `schedule:run` only to dispatch scheduled jobs to workers. Events might me dropped in case the runs take longer to finish.

## Installation
Install via composer:
```
composer require tback/scheduledaemon
```

Then add ServiceProvider to `config/app.php`:
```
...
$providers => [
    //...
    ScheduleDaemon\ServiceProvider::class,
    //..
];
```
## Usage
`php ./artisan schedule:daemon`
