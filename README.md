# Create-EC2-and-install-Apache-try-access-it-through-Load-balancer
Create EC2 and install Apache try access it through Load balancer

Create vpc 10.0.0.0/16
Create igw and attach to vpc
Created public subnet 10.0.0.0/24 in ap-south-1a
Created private subnet 10.0.1.0/24 ap-south-1b
Nat gateway put in public subnet
Created public route table
Associate to pub subnet
Edited route
0.0.0.0/0 target to igw
Created pvt RT
Associate to pvt subnet
Edited routes
0.0.0.0/0 to Nat gateway

create sg to use 22 80 443 SSH HTTP HTTPS POrts
Create EC2 on ubuntu 20.04 in Public subnet
Create EC2 on ubuntu 20.04 in Private subnet
 Try to ssh into public EC2 instance
 ssh -i "PK.pem" ubuntu@pubip
 vi PK.pem
 paste key
 :wq

 Now from public instance (Bastion try to connect pvt instance)
  ssh -i "PK.pem" ubuntu@pvtip
  apt-get update
  upt-get install apache2
  systemctl start apache2
  systemctl status apache2

  Create LB
  Create TG
  register pvt IP

  Copy LB DNS
  Browse with LB-DNS
  we are accessed apache server



