To run the playbook, you need to have Ansible installed on your computer. You can find installation instructions here:  

https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html  

docker-compose.template is a template that will be used for docker-compose.yml generation.  

You also need to specify these variables:  

nodes_count - total amount of Cassandra and Spark worker nodes  
cassandra_memory_limit, spark_memory_limit - memory limit for Cassandra and Spark, positive integer, followed by a suffix of B, K, M, G, to indicate bytes, kilobytes, megabytes, or gigabytes  
cassandra_cpu_limit, spark_cpu_limit - cpu limit. For instance, if the host machine has two CPUs and you set cassandra_cpu_limit=1.5, the container is guaranteed at most one and a half of the CPUs  

Example:  

ansible-playbook generate.yaml --extra-vars "nodes_count=2 cassandra_memory_limit=1G cassandra_cpu_limit=1 spark_memory_limit=1G spark_cpu_limit=1"  
