# PASS

## [Deis](http://deis.io/)
Deis (pronounced DAY-iss) is an open source PaaS that makes it easy to deploy and manage applications on your own servers. Deis builds upon Docker and CoreOS to provide a lightweight PaaS with a Heroku-inspired workflow.

## [Dokku](https://github.com/progrium/dokku)
Docker powered mini-Heroku in around 100 lines of Bash.

## [Flynn](https://flynn.io/)
Flynn deploys apps, scales apps, and manages databases.

## [Tsuru](https://tsuru.io/)
Tsuru is an open source PaaS that makes it easy and fast to deploy and manage applications on your own servers.

## [Octohost](http://www.octohost.io/)
Simple web focused Docker based mini-PaaS server. git push to deploy your websites as needed.

## [Panamax](http://panamax.io/) 
Panamax is a containerized app creator with an open-source app marketplace hosted in GitHub. Panamax provides a friendly interface for users of Docker, Fleet & CoreOS.

# Service Discovery
Service discovery is used so that containers can find out about the environment they have been introduced to without administrator intervention. They can find connection information for the components they must interact with, and they can register themselves so that other tools know that they are available.

## [etcd](https://coreos.com/etcd/)
Service discovery / globally distributed key-value store by CoreOS.

## [consul](https://www.consul.io/)
Service discovery / globally distributed key-value store by hashicorp.

## [zookeeper](https://zookeeper.apache.org/)
Service discovery / globally distributed key-value store by Apache Foudation.

## [crypt](https://xordataexchange.github.io/crypt/)
Store for encrypted configuration parameters from etcd or consul.

## [confd](http://www.confd.io/)
Manages local application configuration files using templates and data from etcd or consul.


# Networking

## [flannel](https://github.com/coreos/flannel)
Flannel is a virtual network that gives a subnet to each host for use with container runtimes.

## [Weave](https://github.com/weaveworks/weave)
Weave creates a virtual network that connects Docker containers deployed across multiple hosts and enables their automatic discovery.

## [Pipework](https://github.com/jpetazzo/pipework)
Pipework lets you connect together containers in arbitrarily complex scenarios. Pipework uses cgroups and namespace and works with "plain" LXC containers (created with lxc-start), and with the Docker.

# Orchestration (scheduling, cluster management, provisioning)

**Cluster management**: controlling a group of hosts

**Scheduling**: loading services on the host system by hooking into host init system or *cluster-wide* init system

## [fleet](https://github.com/coreos/fleet https://coreos.com/using-coreos/clustering/)
Fleet is the scheduling and cluster management component of CoreOS. It reads connection info for each host in the cluster from etcd and provides systemd-like service management.

## [marathon](https://github.com/mesosphere/marathon)
Marathon is the scheduling and service management component of a Mesosphere installation. It works with mesos to control long-running services and provides a web UIfor process and container management.

## [swarm](https://docs.docker.com/swarm/) 
Swarm is a scheduler by Docker team. It hopes to provide a robust scheduler that can spin up containers on hosts provisioned with Docker, using Docker-native syntax.

## [mesos](https://mesos.apache.org/)
Apache mesos is a tool that abstracts and manages the resources of all hosts in a cluster. It presents a collection of the resources available throughout the entire cluster to the components built on top of it (like marathon). It describes itself as analogous to a "kernel" for a clustered configurations.

## [kubernetes](http://kubernetes.io/) 
Google's advanced scheduler, kubernetes allows much more control over the containers running on the infrastructure. Containers can be labeled, grouped, and given their own subnet for communication.

## [compse](https://docs.docker.com/compose/)
Docker's compose project was created to allow group management of containers using declarative configuration files. It uses Docker links to learn about the dependency relationship between containers.

## [Helios](https://github.com/spotify/helios)
Helios is a Docker orchestration platform for deploying and managing containers across an entire fleet of servers, developed by Spotify. 

# Monitoring and management
## [Shipyard](http://shipyard-project.com/)
Built on Docker Swarm, Shipyard gives you the ability to manage Docker resources including containers images, private registries and more.

## [Prometheus](http://prometheus.io/) 
Prometheus is an open-source systems monitoring and alerting toolkit.

# More

## [Surf](https://www.serfdom.io/)
Surf is a decentralized solution for cluster membership, failure detection and orchestration.

## [logspout](https://github.com/gliderlabs/logspout)
Log routing for Docker container logs.

## [Flocker](https://github.com/ClusterHQ/flocker)
Flocker is an open-source Container Data Volume Manager for Dockerized applications.