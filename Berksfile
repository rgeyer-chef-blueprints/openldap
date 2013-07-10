site :opscode

cookbook "openldap",
  path: "~/Code/Chef/me/rgeyer-rs-cookbooks/openldap"  #git: "https://github.com/rgeyer-rs-cookbooks/openldap.git"
cookbook "rightscale_sandbox",
  git: "https://github.com/rgeyer-rs-cookbooks/rightscale_sandbox.git"

cookbook "db",
  git: "git://github.com/rgeyer/rightscale_cookbooks-1.git",
  branch: "openldap_db",
  rel: "cookbooks/db"
cookbook "db_mysql",
  git: "git://github.com/rgeyer/rightscale_cookbooks-1.git",
  branch: "release_20121219",
  rel: "cookbooks/db_mysql"
cookbook "db_postgres",
  git: "git://github.com/rgeyer/rightscale_cookbooks-1.git",
  branch: "release_20121219",
  rel: "cookbooks/db_postgres"
cookbook "block_device",
  git: "git://github.com/rgeyer/rightscale_cookbooks-1.git",
  branch: "release_20121219",
  rel: "cookbooks/block_device"
cookbook "logging",
  git: "git://github.com/rgeyer/rightscale_cookbooks-1.git",
  branch: "release_20121219",
  rel: "cookbooks/logging"
cookbook "logging_rsyslog",
  git: "git://github.com/rgeyer/rightscale_cookbooks-1.git",
  branch: "release_20121219",
  rel: "cookbooks/logging_rsyslog"
cookbook "logging_syslog_ng",
  git: "git://github.com/rgeyer/rightscale_cookbooks-1.git",
  branch: "release_20121219",
  rel: "cookbooks/logging_syslog_ng"
cookbook "rightscale",
  git: "git://github.com/rgeyer/rightscale_cookbooks-1.git",
  branch: "release_20121219",
  rel: "cookbooks/rightscale"
cookbook "sys",
  git: "git://github.com/rgeyer/rightscale_cookbooks-1.git",
  branch: "release_20121219",
  rel: "cookbooks/sys"
cookbook "sys_dns",
  git: "git://github.com/rgeyer/rightscale_cookbooks-1.git",
  branch: "release_20121219",
  rel: "cookbooks/sys_dns"
cookbook "sys_firewall",
  git: "git://github.com/rgeyer/rightscale_cookbooks-1.git",
  branch: "release_20121219",
  rel: "cookbooks/sys_firewall"
cookbook "sys_ntp",
  git: "git://github.com/rgeyer/rightscale_cookbooks-1.git",
  branch: "release_20121219",
  rel: "cookbooks/sys_ntp"

group :vagrant_only do
  cookbook "rs_vagrant_shim",
    path: "~/Code/Chef/me/rgeyer-rs-cookbooks/rs_vagrant_shim/cookbooks/rs_vagrant_shim"
    #git: "https://github.com/rgeyer-rs-cookbooks/rs_vagrant_shim.git",
    #rel: "cookbooks/rs_vagrant_shim"
  cookbook "resolver",
    git: "git://github.com/flaccid/cookbooks.git",
    rel: "cookbooks/resolver"
end