PhpOrient\Client
===============

Class Client




* Class name: Client
* Namespace: PhpOrient
* This class implements: [PhpOrient\Protocols\Common\ConfigurableInterface](PhpOrient-Protocols-Common-ConfigurableInterface.md)


Constants
----------


### DATABASE_TYPE_DOCUMENT

    const DATABASE_TYPE_DOCUMENT = \PhpOrient\Protocols\Common\Constants::DATABASE_TYPE_DOCUMENT





### DATABASE_TYPE_GRAPH

    const DATABASE_TYPE_GRAPH = \PhpOrient\Protocols\Common\Constants::DATABASE_TYPE_GRAPH





### CLUSTER_TYPE_PHYSICAL

    const CLUSTER_TYPE_PHYSICAL = \PhpOrient\Protocols\Common\Constants::CLUSTER_TYPE_PHYSICAL





### CLUSTER_TYPE_MEMORY

    const CLUSTER_TYPE_MEMORY = \PhpOrient\Protocols\Common\Constants::CLUSTER_TYPE_MEMORY





### SERIALIZATION_DOCUMENT2CSV

    const SERIALIZATION_DOCUMENT2CSV = \PhpOrient\Protocols\Common\Constants::SERIALIZATION_DOCUMENT2CSV





### SERIALIZATION_SERIAL_BIN

    const SERIALIZATION_SERIAL_BIN = \PhpOrient\Protocols\Common\Constants::SERIALIZATION_SERIAL_BIN





### STORAGE_TYPE_LOCAL

    const STORAGE_TYPE_LOCAL = \PhpOrient\Protocols\Common\Constants::STORAGE_TYPE_LOCAL





### STORAGE_TYPE_PLOCAL

    const STORAGE_TYPE_PLOCAL = \PhpOrient\Protocols\Common\Constants::STORAGE_TYPE_PLOCAL





### STORAGE_TYPE_MEMORY

    const STORAGE_TYPE_MEMORY = \PhpOrient\Protocols\Common\Constants::STORAGE_TYPE_MEMORY





Properties
----------


#### $hostname
```php
    public string $hostname
```
 The server host.



* Visibility: **public**


#### $port
```php
    public string $port
```
 The port for the server.



* Visibility: **public**


#### $username
```php
    public string $username
```
 The username for the server.



* Visibility: **public**


#### $password
```php
    public string $password
```
 The password for the server.



* Visibility: **public**


#### $_transport
```php
    protected \PhpOrient\Protocols\Common\TransportInterface $_transport
```
 The transport to use for the connection to the server.



* Visibility: **protected**


Methods
-------


### __construct
```php
    mixed PhpOrient\Client::__construct(string $hostname, string $port)
```
##### Class Constructor



* Visibility: **public**


##### Arguments
* $hostname **string** <p>The server host.</p>
* $port **string** <p>The server port.</p>



### setTransport
```php
    \PhpOrient\Client PhpOrient\Client::setTransport(\PhpOrient\Protocols\Common\TransportInterface $transport)
```
##### Sets the transport



* Visibility: **public**


##### Arguments
* $transport **[PhpOrient\Protocols\Common\TransportInterface](PhpOrient-Protocols-Common-TransportInterface.md)**



### getTransport
```php
    \PhpOrient\Protocols\Common\AbstractTransport PhpOrient\Client::getTransport()
```
##### Gets the transport



* Visibility: **public**




### getTransactionStatement
```php
    \PhpOrient\Protocols\Binary\Transaction\TxCommit PhpOrient\Client::getTransactionStatement()
```
##### Start a new Transaction



* Visibility: **public**




### createTransport
```php
    \PhpOrient\Protocols\Binary\SocketTransport PhpOrient\Client::createTransport(\PhpOrient\Protocols\Common\TransportInterface|null $transport)
```
##### Create a transport instance.



* Visibility: **protected**


##### Arguments
* $transport **[PhpOrient\Protocols\Common\TransportInterface](PhpOrient-Protocols-Common-TransportInterface.md)|null**



### execute
```php
    mixed PhpOrient\Client::execute(string $operation, array $params)
```
##### Execute the given operation.



* Visibility: **public**


##### Arguments
* $operation **string** <p>The name of the operation to prepare.</p>
* $params **array** <p>The parameters for the operation.</p>



### connect
```php
    mixed PhpOrient\Client::connect(string $username, string $password, string $serializationType)
```
##### This is the first operation requested by the client when<br />
it needs to work with the server instance.<br />
It returns the session id of the client.



* Visibility: **public**


##### Arguments
* $username **string**
* $password **string**
* $serializationType **string**



### shutDown
```php
    mixed PhpOrient\Client::shutDown(string $username, string $password)
```
##### Send a command to shutdown the server
Requires "shutdown" permission to be set in orientdb-server-config.xml file



* Visibility: **public**


##### Arguments
* $username **string**
* $password **string**



### command
```php
    mixed PhpOrient\Client::command(string $query)
```
##### Execute a not idempotent SQL command



* Visibility: **public**


##### Arguments
* $query **string**



### query
```php
    mixed PhpOrient\Client::query(string $query, integer $limit, string $fetchPlan)
```
##### Execute an idempotent SQL command ( Select usually )



* Visibility: **public**


##### Arguments
* $query **string**
* $limit **integer**
* $fetchPlan **string**



### queryAsync
```php
    mixed PhpOrient\Client::queryAsync(string $query, Array $params)
```
##### Execute an idempotent SQL command in Async mode( Select usually )<br />
A callback function is needed



* Visibility: **public**


##### Arguments
* $query **string**
* $params **Array**



### sqlBatch
```php
    mixed PhpOrient\Client::sqlBatch(string $param)
```
##### Execute an SQL Batch Script command<br />



* Visibility: **public**


##### Arguments
* $param **string**



### recordUpdate
```php
    \PhpOrient\Protocols\Binary\Operations\RecordUpdate|\PhpOrient\Protocols\Binary\Data\Record PhpOrient\Client::recordUpdate(\PhpOrient\Protocols\Binary\Data\Record $record)
```
##### Update a Record



* Visibility: **public**


##### Arguments
* $record **[PhpOrient\Protocols\Binary\Data\Record](PhpOrient-Protocols-Binary-Data-Record.md)**



### recordCreate
```php
    \PhpOrient\Protocols\Binary\Operations\RecordCreate|\PhpOrient\Protocols\Binary\Data\Record PhpOrient\Client::recordCreate(\PhpOrient\Protocols\Binary\Data\Record $record)
```
##### Create a record



* Visibility: **public**


##### Arguments
* $record **[PhpOrient\Protocols\Binary\Data\Record](PhpOrient-Protocols-Binary-Data-Record.md)**



### recordDelete
```php
    \PhpOrient\Protocols\Binary\Operations\RecordDelete|\PhpOrient\Protocols\Binary\Data\Record PhpOrient\Client::recordDelete(\PhpOrient\Protocols\Binary\Data\ID $rid)
```
##### Delete a Record



* Visibility: **public**


##### Arguments
* $rid **[PhpOrient\Protocols\Binary\Data\ID](PhpOrient-Protocols-Binary-Data-ID.md)**



### recordLoad
```php
    \PhpOrient\RecordLoad/Record PhpOrient\Client::recordLoad(\PhpOrient\Protocols\Binary\Data\ID $rid, array $params)
```
##### Load a Record



* Visibility: **public**


##### Arguments
* $rid **[PhpOrient\Protocols\Binary\Data\ID](PhpOrient-Protocols-Binary-Data-ID.md)**
* $params **array**



### dbSize
```php
    integer|string PhpOrient\Client::dbSize()
```
##### Get the size of a Database



* Visibility: **public**




### dbReload
```php
    \PhpOrient\Protocols\Common\ClusterMap PhpOrient\Client::dbReload()
```
##### Reload the structure of a Database



* Visibility: **public**




### dbRelease
```php
    mixed PhpOrient\Client::dbRelease(string $db_name, string $storage_type)
```
##### Release the structure of a Database



* Visibility: **public**


##### Arguments
* $db_name **string**
* $storage_type **string**



### dbOpen
```php
    \PhpOrient\Protocols\Common\ClusterMap PhpOrient\Client::dbOpen(string $database, string $username, string $password, string $dbType)
```
##### Open a Database and perform a connection<br />
if it is not established before



* Visibility: **public**


##### Arguments
* $database **string**
* $username **string**
* $password **string**
* $dbType **string**



### dbList
```php
    array PhpOrient\Client::dbList()
```
##### List all databases inside OrientDB instance



* Visibility: **public**




### dbFreeze
```php
    boolean PhpOrient\Client::dbFreeze(string $db_name, string $storage_type)
```
##### Freeze a database ( need Release to unlock )<br />
Flushes all cached content to the disk storage and allows to perform only read commands



* Visibility: **public**


##### Arguments
* $db_name **string**
* $storage_type **string**



### dbExists
```php
    boolean PhpOrient\Client::dbExists($database, string $database_type)
```
##### Check if a database exists



* Visibility: **public**


##### Arguments
* $database **mixed**
* $database_type **string**



### dbDrop
```php
    mixed PhpOrient\Client::dbDrop($database, string $storage_type)
```
##### Drop an existent database



* Visibility: **public**


##### Arguments
* $database **mixed**
* $storage_type **string**



### dbCreate
```php
    boolean PhpOrient\Client::dbCreate(string $database, string $storage_type, string $database_type)
```
##### Create a new Database



* Visibility: **public**


##### Arguments
* $database **string**
* $storage_type **string**
* $database_type **string**



### dbCountRecords
```php
    integer|string PhpOrient\Client::dbCountRecords()
```
##### Create a new Database



* Visibility: **public**




### dbClose
```php
    integer PhpOrient\Client::dbClose()
```
##### Close a database a drop the connection



* Visibility: **public**




### dataClusterDrop
```php
    boolean PhpOrient\Client::dataClusterDrop(integer $cluster_id)
```
##### Drop a data cluster



* Visibility: **public**


##### Arguments
* $cluster_id **integer**



### dataClusterDataRange
```php
    array<mixed,integer>|array<mixed,string> PhpOrient\Client::dataClusterDataRange(integer $cluster_id)
```
##### Returns the range of record ids for a cluster.



* Visibility: **public**


##### Arguments
* $cluster_id **integer**



### dataClusterCount
```php
    integer|string PhpOrient\Client::dataClusterCount(array $cluster_ids)
```
##### Returns the number of records in one or more clusters.



* Visibility: **public**


##### Arguments
* $cluster_ids **array**



### dataClusterAdd
```php
    integer PhpOrient\Client::dataClusterAdd($cluster_name, string $cluster_type)
```
##### Add a new data cluster



* Visibility: **public**


##### Arguments
* $cluster_name **mixed**
* $cluster_type **string**



### configure
```php
    \PhpOrient\Protocols\Common\ConfigurableInterface PhpOrient\Protocols\Common\ConfigurableInterface::configure(array $options)
```
##### Configure the object.



* Visibility: **public**
* This method is defined by [PhpOrient\Protocols\Common\ConfigurableInterface](PhpOrient-Protocols-Common-ConfigurableInterface.md)


##### Arguments
* $options **array** <p>The options for the object.</p>



### fromConfig
```php
    static PhpOrient\Client::fromConfig(array $options)
```
##### Return a new class instance configured from the given options.



* Visibility: **public**
* This method is **static**.


##### Arguments
* $options **array** <p>The options for the newly created class instance.</p>

