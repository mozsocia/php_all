Sure thing! If you're looking for a simple logger in raw PHP, you can create a basic one like this:

```php
// Logger.php
class Logger {
    private $logFile;

    public function __construct($logFile = 'app.log') {
        $this->logFile = $logFile;
    }

    public function log($message) {
        $timestamp = date('[Y-m-d H:i:s]');
        $logEntry = "$timestamp $message" . PHP_EOL;
        file_put_contents($this->logFile, $logEntry, FILE_APPEND);
    }
}
```
#### Example usage:
```php
require_once 'Logger.php';

$logger = new Logger();
$logger->log('This is a log message.');


$sql = "SELECT * FROM patient WHERE email= '" . $_POST["email"] . "' AND password= '" . $_POST["password"] . "'";
    
// Execute the SQL query
$result = $conn->query($sql);

// Log the $result variable
$logger->log('Query Result: ' . print_r($result, true));
```

This logger class has a constructor that allows you to specify the log file (default is 'app.log'). The `log` method adds a timestamp to the provided message and appends it to the log file.

Feel free to customize it based on your needs!
