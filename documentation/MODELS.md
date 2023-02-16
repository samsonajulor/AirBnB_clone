# ALXBnB - Models Class System :cl:

ALXBnB supports the following classes:

* [BaseModel](../models/base_model.py)
* [User](../models/user.py)
* [State](../models/state.py)
* [City](../models/city.py)
* [Amenity](../models/amenity.py)
* [Place](../models/place.py)
* [Review](../models/review.py)

<p align="center">
  <img src="https://github.com/samsonajulor/ALXBnB/blob/master/assets/alx-models.png"
       alt="ALXBnB logo"
       width="750"
  >
</p>

[Source code.](../models)

## Storage :baggage_claim:

The above classes are handled by one of either two abstracted storage engines,
depending on the call - [FileStorage](../models/engine/file_storage.py) or
[DBStorage](../models/engine/db_storage.py).

### FileStorage

The default mode.

In `FileStorage` mode, every time the backend is initialized, ALXBnB
instantiates an instance of `FileStorage` called `storage`. The `storage`
object is loaded/re-loaded from any class instances stored in the JSON file
`file.json`. As class instances are created, updated, or deleted, the
`storage` object is used to register corresponding changes in the `file.json`.

### DBStorage

Run by setting the environmental variables `ALX_TYPE_STORAGE=db`.

In `DBStorage` mode, every time the backend is initialized, ALXBnB
instantiates an instance of `DBStorage` called `storage`. The `storage` object
is loaded/re-loaded from the MySQL database specified in the environmental variable
`ALX_MYSQL_DB`, using the user `ALX_MYSQL_USER`, password `ALX_MYSQL_PWD`, and
host `ALX_MYSQL_HOST`. As class instances are created, updated, or deleted, the
`storage` object is used to register changes in the corresponding MySQL database.
Connection and querying is achieved using SQLAlchemy.

Note that the databases specified for `DBStorage` to connect to must already be
defined on the MySQL server. This repository includes scripts
[setup_mysql_dev.sql](../mysql/setup_mysql_dev.sql) and [setup_mysql_test.sql](../mysql/setup_mysql_test.sql)
to set up `alx_dev_db` and `ALX_test_db` databases in a MySQL server,
respectively.

## Author :black_nib:

* __Samson Ajulor__ - <[samsonajulor](https://github.com/samsonajulor)>
