= Usage

Copy runlists/openldap-producer/default.json.example to runlists/openldap-producer/default.json and enter your credentials for sys_dns and block_device
Copy runlists/openldap-consumer/default.json.example to runlists/openldap-consumer/default.json and enter your credentials for sys_dns and block_device

Fire up a producer

    bundle exec vagrant up producer
    runlist="do_create_database" bundle exec vagrant provision producer
    runlist="do_init_and_become_master" bundle exec vagrant provision producer

Fire up a consumer

    bundle exec vagrant up consumer
    runlist="do_init_and_become_consumer" bundle exec vagrant provision consumer

= TODO

* https://github.com/rgeyer-rs-cookbooks/openldap/blob/master/README.md
* Should all newly created DB's have syncrepl added once a server is tagged/identified as a "producer"
* Should consumers have DNS hostnames and update capability?
