Managing your stateless and stateful applications with the Kubernetes provides efficiencies and simplifies automation. However, before using StatefulSets for your own stateful applications, you should consider if any of the following apply:

- You embrace microservices
- You frequently create new service footprints that include stateful applications
- Your current solution for storing state can't scale to meet predicted demand
- Your stateful applications can meet performance requirements without using specialized hardware and could effectively run on the same hardware used for stateless applications
- You value flexible reallocation of resources, consolidation, and automation over squeezing the most and having highly predictable performance

If any of the previous bullets apply to your situation, it may make sense to use Kubernetes for your stateful applications.

cat &lt;<EOF &gt; mysql-configmap.yaml

apiVersion: v1

kind: ConfigMap

metadata:

 name: mysql

 labels:

 app: mysql

data:

 master.cnf: |

 \# Apply this config only on the master.

 \[mysqld\]

 log-bin

 slave.cnf: |

 \# Apply this config only on slaves.

 \[mysqld\]

 super-read-only

EOF

———————

cat &lt;<EOF &gt; mysql-services.yaml

\# Headless service for stable DNS entries of StatefulSet members.

apiVersion: v1

kind: Service

metadata:

 name: mysql

 labels:

 app: mysql

spec:

 ports:

 \- name: mysql

 port: 3306

 clusterIP: None

 selector:

 app: mysql

\-\-\-

\# Client service for connecting to any MySQL instance for reads.

\# For writes, you must instead connect to the master: mysql-0.mysql.

apiVersion: v1

kind: Service

metadata:

 name: mysql-read

 labels:

 app: mysql

spec:

 ports:

 \- name: mysql

 port: 3306

 selector:

 app: mysql

EOF

———————