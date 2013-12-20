#node-mysql2 without dependency

Mysql client for node.js. Written in native JavaScript and aims to be mostly api compatible with [node-mysql](https://github.com/felixge/node-mysql)
[node-mysql2](https://github.com/sidorares/node-mysql2)

## Features

 In addition to client-side query/escape and connection pooling

  - MySQL server API for proxies and mocks
  - SSL and compression
  - prepared statements

## Documentation

See [node-mysql](https://github.com/felixge/node-mysql) documentation.

## Examples

Simple select:

```js
var mysql      = require('./node-mysql2');
var con = mysql.createConnection({
  host     : 'x.x.x.x',
  user     : 'xxx',
  password : 'xxx',
  database : 'xxx'
});
con.on('error',function(e) {
	console.log('ERROR: '+e);
});

con.connect();
con.query('SELECT * FROM `testtable`', function(err, rows, fields) {
	  if (err) return console.log(err);
	  console.log(rows);
});
con.end();
```

Prepared statement and parameters:

```js
var mysql      = require('mysql2');
var connection = mysql.createConnection({ user: 'test', database: 'test'});

connection.execute('SELECT 1+? as test1', [10], function(err, rows) {
  //
});
```

## License

 MIT

## Benchmarks
  - see [node-mysql-benchmarks](https://github.com/mscdex/node-mysql-benchmarks)
  - try to run example [benchmarks](https://github.com/sidorares/node-mysql2/tree/master/benchmarks) on your system

