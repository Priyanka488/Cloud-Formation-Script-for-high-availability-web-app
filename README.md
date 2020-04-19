<img src="header.png"/>

# Deploy a high availability web app using Cloud Formation Script

### Infrastructure Diagram

<img src="Infrastructure Diagram.png"/>

### Files and Functions

- <a href="network_infrastructure.yml">network_infrastructure.yml</a> : Stack that creates a VPC, Internet gateway, Internet gateway attachment, 2 Public Subnets, 2 Private Subnets, 2 NAT Gateways deployed in public subnets, Routing Table and Rules for Private and Public Subnets. 

- <a href="network-params.json">network-params.json</a> : Parameter file for the network infrastructure.

- <a href="server_securityGroups.yml">server_securityGroups.yml</a> : Stack that creates security group for Load Balancer and Web Server, Launch configuration for Auto Scaling Group, Load Balancer alongwith Listeners, listener rules and target groups. It also outputs the Load Balancer URL. 

- <a href="server-params.json">server-params.json</a> : Parameter file for the servers infrastructure.

### Commands to run the scripts

1. To create the network infrastructure stack :

```
chmod +x create.sh
./create.sh <stack_name> network_infrastructure.yml network-params.json
```
2. To update the network infrastructure stack :

```
chmod +x update.sh
./update.sh <stack_name> network_infrastructure.yml network-params.json
```
3. To create the servers infrastructure stack :

```
chmod +x create.sh
./create.sh <stack_name> server_securityGroups.yml server-params.json
```

4. To update the servers infrastructure stack :
```
chmod +x update.sh
./update.sh <stack_name> server_securityGroups.yml server-params.json
```


### URLS

1. Load balancer URL : http://myser-webap-73zilc1pvvo4-598412498.us-west-2.elb.amazonaws.com/
2. Index file in S3 with public access: https://priyanka-udagram.s3-us-west-2.amazonaws.com/index.html


