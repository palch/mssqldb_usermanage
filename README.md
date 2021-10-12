Role Name
=========

mssqldb_usermanage role can be used to create,drop,grant role,revoke role for users on MSSQL Server databases


Role Variables
--------------

Either domain user or sql user can be given and both also.

```
manage:
  list:
    - user:
        - name: <domain_name>\<user_name>
      ensure: present
      type: WindowsUser
    - user:
        - name: <user_name>
          password: xxxxxxxx
      ensure: present
      type: SqlLogin

  role:
    - serverrole: <role_name>
      user: 
        - <user_name>
        - <domain_name>\<user_name>
      ensure: present
```


Dependencies
------------

Needed SqlServerDsc powershell module to be installed.

Example Playbook
----------------


    - hosts: servers
      roles:
         - mssqldb_usermanage

ansible-playbook playbook.yml 

