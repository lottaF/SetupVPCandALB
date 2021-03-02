# SetupVPCandALB
Contains two CLoudformation stack files:
- One setting up a new VPC with two subnet pairs a private and a public - in 
  two separate availability zones. (add short description on gateways etc)
- One setting up ASG, SG, TG, ALB, Listeners in AWS in a specified VPC.

Instructions:

    Open the file ’AnnsVPC.yaml’, check and edit the input-parameters declared in top of file:
    - Environment (string): Name of the VPC and used as prefix in network resources
      Default ’AnnsCloud’.
    - VpcCIDR (string): IP range for the network in CIDR notation. If the pre-defined range is 
       free and preferred, there is noo need to update this nor the subnetwork IP ranges.
    - PubSubn1CIDR, PubSubn2CIDR, PrivSubn1CIDR, PrivSubn1CIDR: IP ranges for the respective 
      subnetworks. 
 
    Build a stack based ion this file.
    
    Open the file ’VeraALB.yaml’, check and edit the input-parameters declared in top of file.
    From the utput of the "Ann-VPC stack", copy result into the parameters of 'VeraALB' as follows:
      

        MyVpc: 	    Copy Value of ’VPC’ in Output.
        MySubn1:	Copy Value of ’PrivSubn1’ i Output.
        MySubn2:	Copy Value of ’ PrivSubn2’ i Output.
        MyPubSubn1:	Copy Value of ’ PubSubn1’ i Output.
        MyPubSubn2	Copy Value of ’ PubSubn2’ i Output.

    Set remaining parametrar as this:
    
    DevEnvCIDR:     State the IP range of the development environment that need ssh-access.
  
    NameOnPage:     State the name to put on the web-page.

    KeyPairKey: 	State the name of the security key to use when generating the webservers.



