Webhop - Bootstrap MySQL for Vagrant
=====================================

Ansible role to install requirements and restore a mysqldump into a vagrant machine


## Requirements

Requires a working python 2.7 installation in the base vagrant box being used


## Role Variables

##### Defaults

- `mysql_user` - User to create in the mysql database (**root**)
- `mysql_password` - Password to set in mysql for the mysql_user. Note that this has no effect when using root user.
- `mysql_database` - MySQL database name for the database. (**database**)
- `mysql_prefix` - Optional prefix for drupal database.


##### Variables

- `region` - Region to use when restoring the DB and/ or file dump
- `aws_credentials` - Amazon Web Service credentials for restore actions
- `s3_bucket` - S3 bucket name for restore actions
- `database_backup_name` - Database archive object name in the s3 bucket
- `files_backup_name` - Files archive object name in the s3 bucket

Usage
-----

```yaml
roles:
    - { role: webhop.restoredb,
        database_backup_url: https://s3.amazonaws.aws.com/sites/backups/mysite.zip,
        restore_db_backup: true
    }
```

Author Information
------------------

* Neil Saunders - neil@beamly.com
* Vik Bhatti - vik@beamly.com
