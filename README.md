# VPC-Peering-Connection 
In this project we will be establishing VPC Peering connections between the Marketing department, the Finance department, and the Developer department.

## Prerequisites 
You will need access to the AWS console, EC2, VPC, and github(for documentaiton)

## Step: 1 Long into the AWS console
- go and select the VPC service
- In the left navigation pane click "Your VPC"
- Review the marketing, Finance, and developer VPC

## Step 2: Go back to EC2 services 
- click on the EC2 services
- Go to the resources sections, then click instances (running)
- next choose and select the finance instance service
- go to the detials tab and reiveiw the information.
- Copy the private IP addresses for the Private VPC
- Click and choose marketing VPC IP, and click connect at the top

## Step 3: Connect to Terminal 
- use copied IP address, and run command "ping" then paste the address after ping
- run the command to verify the commmand
- Exit the terminal by pressing control C

## Step 4: Head back to EC2 instances 
- Under Instance ID click marketing Instance ID
- Under Subnet ID click and then go to the Route table
- click the link, and choose marketing route table
- Review the routing rules

## Step 5: Setup peering connection, go to left navigation pane
- In the peering connection, then create a new peering connection
- In peering connection name type "Marketing <> Finance"
- Select VPC to peer with, then review the CIDR
- For VPC connector choose finance VPC, review CIDR
- Click create peering connection
- Look for green success messege then under actions choose accept request and click

## Step 6: Return to Instances
- Choose marketing instances, then click subnet ID link
- In the subnet section select the marketing box
- Click Route table
- Click marketing route tables, then click edit routes
- click add route table and type 172.31.0.0/16
- For target box choose peering connection
- Then choose "Marketing <> Finance, then click save changes

 ## Step 7: Go back to instance section
- Clcik the finance instance and select the check box
- Click subnet ID, in the subnet section click route table
- In the route table section click edit routes
- Add route, type 10.10.0.0/16
- Select peering connection then click marketing <> finanace
- Clcik save and then wait for the success messege to pop up

## Step 8: Go back to EC2 instance
- click to connect to the terminal
- Run command ping and replace the current IP address with the one that was copied
- make sure its the IP address for finance
- Run the command to check if it is running (should not be)
- Press Control C to exit Terminal

## Step 9: Head back to EC2 instances, click the finace checkbox
- clcik security tab, then click the security group link
- Click inbound rules, then click edit inbound rules
- click to add rule
- Choose Custom ICMP - IPV4, and then type 10.10.0.0/16
- Click save rules

## Step 10: Connect to Terminal
- Run ping command and paste the IP address
- Review the data
- The marketing server should now be able to communicate with Finance
- Press Control C to exit terminal

# At the end of this project peering connections should be established between each departement.
