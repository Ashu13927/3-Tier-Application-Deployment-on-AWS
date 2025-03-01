# 3-Tier-Application-Deploy-on-AWS

steps

step 1 : Create VPC 

step 2 : Vpc >> Create nat gateway 

step 3 : Attache nate gatewat to private subnet 

step 4 : Ec2 create 

 // now launch public ec2 instance for access private Ec2
	 
step 5 : Create load balancer (left side of ec2) 

//  Create connectivity between private or public Ec2 instance 

//  Target group  go in your target group >> register targets >> select both private ec2 instance 

step 6 : RDS “rds connect to ec2”  create database
   
	 now connect rds or ec2



Check // open terminal & connect to ec2  (now you are login public server) >> type sudo –I (now login private server)
			telnet use for check connectivity 			 yum install telnet
		now copy rds “end point”       type (telnet “paste endpoint” 3306)




// 3 tier application deployment  like Amazon website or google search engine (user search on website front end ‘tier 1’ to process in back end ‘tier 2’ to database ‘tier 3’  if database give ans to user )

// 2 tier  like form filling, applying form, contact form (front end ‘tier 1’ to back end ‘tier 2’ to database ‘tier 3’  but in database not sending any data to users)
