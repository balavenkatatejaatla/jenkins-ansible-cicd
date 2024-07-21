student_app_setup/
├── ansible.cfg
├── inventory
│   ├── development
│   ├── staging
│   └── production
├── group_vars
│   ├── development
│   │   └── vars.yml
│   ├── staging
│   │   └── vars.yml
│   └── production
│       └── vars.yml
├── playbook.yml
├── Jenkinsfile
└── roles
    ├── common
    │   └── tasks
    │       └── main.yml
    ├── java
    │   └── tasks
    │       └── main.yml
    ├── tomcat
    │   ├── files
    │   │   └── tomcat.service
    │   ├── tasks
    │   │   ├── install.yml
    │   │   ├── service.yml
    │   │   ├── configure.yml
    │   │   └── main.yml
    │   └── templates
    │       └── context.xml.j2
    ├── mysql
    │   ├── tasks
    │   │   ├── install.yml
    │   │   ├── configure.yml
    │   │   ├── main.yml
    │   │   └── create_db.yml
    │   └── templates
    │       └── my.cnf.j2
    └── deploy
        └── tasks
            └── main.yml
