# go-email-verifier-tool
Simple email verifier tool that checks if a email domain exist or not by looking at its records. The verifier will give back the domain names records, and will check for the ```hasMX``` records and ```hasSPF``` recrods. If it has any of the records, it will give them by returning ```spfRecord```, ```hasDMARC``` and ```dmarcRecord```.

## Prerequisites
- Download and install Go (https://golang.org/dl/)

## Run code
In this project folder, run in terminal ```go run main.go```. 

## Example
After running the main go file, you will get the following in the terminal:
```
domain, hasMX, hasSPF, spfRecord, hasDMARC, dmarcRecover
``` 
Type in the domain name you want to test. For example, to test if netlight has avalid domain name, type ```netlight.com``` and press enter. You should get something like this 
```
netlight.com, true, true, v=spf1 include:spf.protection.outlook.com include:mail.zendesk.com include:_spf.salesforce.com -all, true, v=DMARC1; p=quarantine; pct=100; rua=mailto:svcDmarcMonitor@netlight.com; ruf=mailto:svcDmarcMonitor@netlight.com
``` 

It will give ```netlight.com``` as the domain. It has MX records and SPF records, since they are both true. It also has spf records and DMARC, with its records. Indeed the domain ```netlight.com``` seems to be avalid domain. 