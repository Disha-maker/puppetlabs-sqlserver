##2016-07-12 - Supported Release 1.1.3
###Summary

- Small release with several bug fixes and minor features
- Updated the supported Puppet version ranges

####Features
- Updated documentation with more advanced SQL example
- Add Windows Based Authentication for `sqlserver::config`. Modifies the `sqlserver::config` class with an additional property called `login_type` which can be either `SQL_LOGIN` or `WINDOWS_LOGIN`, with a default of `SQL_LOGIN`

####Bug Fixes
- Fix Role Name Collisions. This fix introduces the database name into the title created for the `sqlserver_tsql` statements so that it is unique
- Minor refactoring of code which is not used or make code path more obvious
- Fix TSQL error propagation. Introduce a minor refactor so that the `returns` property captures errors properly from TSQL executions
- Emit debug output on failed `onlyif` TSQL. Previously, there was no way of getting the log output from SQL Server when executing TSQL during an `onlyif`

##2016-04-11 - Supported Release 1.1.2
###Summary

Small release to support Puppet version ranges.


##2015-12-08 - Supported Release 1.1.1
###Summary

Small release for support of newer PE versions.

##2015-09-08 - Supported Release 1.1.0
###Summary

User, Roles and Login as well as they permissions associated with each are now available.

####Features
- `sqlserver_instance` and `sqlserver_features` have new parameter `install_switches` which takes a hash of install switches and writes them to a temp configuration file for the the install process
- Add define for permissions for Users, Roles and Logins
- `sqlserver::config` no longer writes a file to the sytem
- New `sqlserver_tsql` provider available to execute custom scripts
- Remove dependency on 'sqlcmd.exe'
- Performance discovery improvements
- Remove dependency for ACL modules

####Bug Fixes
- Munge values for instance names to always be uppercase when comparing
- Change the way we look up logins to use sys.server_principals instead of function that might not report correctly
- Fix issue with collation_name and databases where the variable was not named properly causing it to never be set

##2014-12-08 - 1.0.0
Initial release
