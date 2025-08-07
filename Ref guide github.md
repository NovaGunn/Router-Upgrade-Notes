# Cyber Essentials Upgrade Kit - Router License and Upgrade Notes
# Senstive information redacted. 
# Last updated: 07/08/2025

Tasks: 



Cyber Essentials Upgrade kit: (last one)
- router
- Request for Change
- Plan for downtime 
- Let personA or PersonB know to alert customers of downtime
- Make sure PersonC is available as well the same day in case soemthing goes wrong

- it has HSECk9-ALT license - we need to find the UDI and search the cisco web portal for the license 
- Throughput and Security K9 is a standard fix
-
- Check the Licenses on the device 
-
- install add file flash:isr4400.17.12.05a.SPA.bin activate commit
- 
- Check config hasn't been stripped 
-
-
- If license remove:
 - conf t
 - license boot level securityk9
 - platform hardware throughput level 100000
 -
	(Redacted)
 - UDI: <Redacted_UDI>
 - SN:  <Redacted_SN>
-
-
- This process is for devices which are airgapped: 
	- NO Connectivity to CSSM and No CLSU
	- CLSU disconnected from CSSM
	- SSM On-Prem Deployment (product instance-initiated and SSM On-Prem-initiated Communication) 
-
-
- HSECk9-ALT 
 - Probably going to be removed:
	- There is 2 options SLAC or SLR:

			(SLR)
		   
			- conf t
			- license smart reservation 
				- to enable other commands in privilege mode: 
					- license smart reservation request local
				- this should give us the necessary unique ID to enter into the cisco web portal 
		  
		    (SLAC) - Wont work - we need transport type to be SSM on-prem which it isn't. 
		  - to use SLAC (Smart License Authorisation Code)
		  - log into the cisco SSM (Smart software manager)
		  - Click inventory
		  - Click the Product instances tab
		  - Click the authorisation License Enforced Features
		  - Generate SLAC for a single product instance: 
			- Enter PID and Serial Number 
				- Do not populate any of the other fields
			- Choose the license and reserve 1
			- Click Next
			- Generate Authorisation Code
			- Download the authorisation code and save as a .csv file 
			
			
- PROBLEM!! 

- Turns out the device doesn't exist within our CSSM portal and pre-dates any of my colleagues knowledge.
- Meaning upgrading the router is not possible unless we know that. Which in this case means a replacement, not an upgrade job. 
