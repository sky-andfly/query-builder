# SIMPLE QUERY BUILDER
___
## Connection
Connect the file `QueryBuilder.php` to your project:
```php
require_once "databases/QueryBuilder.php";
```
To create a class object, you need to pass a connection of the PDO type:
```php
 $db = new QueryBuilder(Connection::make());
```
## Using 
___
You can use the following methods  to access the databases:
```php
->getAll($table);
->search($table, $text);
->create($table, $data);
->getOneById($table, $id);
->update($table, $data, $id);
->delete($table, $id);
```
## Example
___
```php
$db = new QueryBuilder(Connection::make($config['database']));

if (isset($_POST['send'])){
    $posts = $db->search('tasks', $_POST['search']);
}else{
    $posts = $db->getAll('tasks');
}
```