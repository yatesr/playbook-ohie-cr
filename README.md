Role Name
========

openempi

Role Variables
--------------
```
openempi_install_dir: /opt/openempi
openempi_version: 3.0.0-beta
openempi_download_url: https://kenai.com/projects/openempi/downloads/download/openempi-entity-{{openempi_version}}-openempi-entity.tar.gz
# Default is for use with yatesr.tomcat-standalone role
openempi_tomcat_dir: "{{tomcat_install_dir}}/apache-tomcat-{{tomcat_version}}"
openempi_java_opts: "-Xms1024m -Xmx1024m -XX:NewSize=256m -XX:MaxNewSize=356m -XX:PermSize=256m -XX:MaxPermSize=356m"
openempi_java_home: "{{java_install_dir}}/jre{{java_version_3}}"
# limited user account that will run openempi and tomcat standalone
openempi_user: openempi
tomcat_user: "{{openempi_user}}"
# Name of tomcat service
tomcat_service: tomcat_standalone
# OpenEMPI DB
openempi_db_name: openempi
openempi_db_user: openempi
openempi_db_password: "openempi"

```

Example Playbook
-------------------------
### playbook.yml

```

---
- hosts: all
  roles:
  - yatesr.java-standalone
  - yatesr.tomcat-standalone
  - yatesr.ohie-cr


```

License
-------

Apache 2.0

Author Information
------------------

Ryan Yates
