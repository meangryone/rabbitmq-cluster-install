# rabbitmq-cluster-install

Requed settings can be set in group vars

# set up admin user for management gui
rabbitmq_management_user            : username
rabbitmq_management_password        : password

# set up tcp port for management gui
rabbitmq_management_port            : set port

# set up message query
# https://www.rabbitmq.com/maxlength.html
rabbitmq_message_query_policy_name  : test
rabbitmq_message_query              : 10


# set up cluster cookies
rabbitmq_cluster_cookie             : cookie 
