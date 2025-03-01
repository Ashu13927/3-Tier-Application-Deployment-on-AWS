# 3-Tier-Application-Deploy-on-AWS

steps

step 1 : Vpc  create vpc >> ✅ Vpc & more >> auto-generate (fill name) >> ✅ no IPv6 cidr block >> availability zone ‘2’ >> public or private subnet ‘2’ >> you can customize (subnets cidr block  write in last size ’28’ instead of ’20’ in every line) >> nat gateway or vpc endpoint ‘none’ >> create 


step 2 : Vpc >> Nat Gateway “in left side”  create nat gateway >> put name >> subnet “choose public subnet” >> connectivity ✅ public >> click button “allocate elastic ip” >> create 

step 3 : Attache nate gatewat to private subnet  go subnet >> select 1 subnet ‘private1’ >> route table (it’s link type) >> routes >> edit routes >> add routes (0.0.0.0/0 – select nate gateway – save changes) 
				 go subnet >> select 1 subnet ‘private2’ >> route table (it’s link type) >> routes >> edit routes >> add routes (0.0.0.0/0 – select nate gateway – save changes) 

step 4 : Ec2 create  amazon – ssh,http,https – network setting (Edit >> select your VPC >> select subnet ‘private1’ ) >> luanch
	  amazon – ssh,http,https – network setting (Edit >> select your VPC >> select subnet ‘private2’ ) >> launch
	// now launch public ec2 instance for access private Ec2
	  amazon – ssh,http,https – network setting (Edit >> select your VPC >> select subnet ‘public1’ >> enable “auto assign…” >> select existing security group ) >> launch
step 5 : Create load balancer (left side of ec2)  create load balancer >> create “application load balancer” >> name >> ✅ internet facing or ipv4 >> net. Mapping (select your Vpc) – mappings (✅ us-east-1a “select (public1)” - ✅ us east 1b “public2”) >> security group “default or launch wizard 2” >> 
	 listeners & reuting (create target group “instance – name – ✅http1” – next - create) than “select your target group” >> create
