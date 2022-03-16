# Project 1 Azure Cloud Environment

## Description of the Azure deployment

In this deployment we designed multiple virtual networks, machines, and network security groups. I will use this space to describe each section in detail as to what we created and what they do.
   
## List of assets created 

   - 2 Web Servers
   - 1 Load Balancer
   - 2 Network Security Groups 
   - 2 Virtual Networks
   - 1 Jump-Box
   - 1 Peering Group

![image](https://user-images.githubusercontent.com/79530988/153937504-9ae30957-b4cd-4e11-a2df-de3ce8b6b53d.png)

## Inbound Security Rules

These pictures below are a vizualization of the working inbound security rules that were ceated with a "zero trust" architecture in mind.
I started with a "DEFAULT DENY" rule in both NSG's (Network Security Group) to the network to protect the network prior to creting these rules that gave access to the networks. In the RedTeam NSG 
the rules are designed to allow one workstation to access the JumpBox Provisioner and Load Balancer protecting the web servers. In the ELK Stack NSG I am allowing the two networks to access eachother
and trnasfer the data that the Metricbeat and Filebeat utilities to function properly and also have the same protection that the RedTeam NSG has from external sources of access. 

#### RedTeam NSG Inbound Security Rules

![image](https://user-images.githubusercontent.com/79530988/153948584-9d865cc5-698d-46fc-ae4f-1556e32ff102.png)

#### ELK Stack NSG Inbound Security Rules

![image](https://user-images.githubusercontent.com/79530988/153948894-22df89ee-0b3a-4bf4-b680-b7ab0454b7fc.png)

## How the assets were configured

Below you will find examples of how the various configuartion files were changed to make the entire network talk and display the data we were seeking while deploying this configuration. 
The original files were downloaded and modified with the data below.

#### Hosts File Changes 

![image](https://user-images.githubusercontent.com/79530988/153943248-37a1dccf-be08-4c8c-b6bc-959003db1bbc.png)

#### Ansible Configuation File Changes 

![image](https://user-images.githubusercontent.com/79530988/153942986-c1287964-7499-4429-9250-38ac147311d8.png)

#### Filebeat Configuartion File Changes 

##### Elastisearch output

![image](https://user-images.githubusercontent.com/79530988/153940586-7be124ab-a658-4847-8aa0-1406618ab0de.png)

##### Kibana Access

![image](https://user-images.githubusercontent.com/79530988/153941773-1daf824f-0f43-445b-ba0c-e22b37e43f85.png)

#### Metricbeat Configuration File Changes 

##### Elastisearch output

![image](https://user-images.githubusercontent.com/79530988/153942008-89e5b8aa-9eee-4e6c-a871-10ce7394b003.png)

##### Kibana Access

![image](https://user-images.githubusercontent.com/79530988/153942199-a6eb8b1b-a668-447f-ac35-0debb8e570b0.png)

## Links to YAML Files 

[ELK YML](/ansible/filebeat/Filebeat Config.yaml)
