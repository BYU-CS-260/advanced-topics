# Configuring a Domain

In this tutorial, you will setup a DNS configuration for a server that is hosted with Digital Ocean. 
The Domain Name Service (DNS) allows you to translate the name of the server you want to connect to (e.g. emmasmith.org) 
into the IP address of this server (e.g. 176.32.98.166).

We will show you how to use DNS and Nginx to serve your website on a domain of your choosing, for example emmasmith.org.

Doing this involves the following steps:

## Obtain a Domain Name
### Option 1: AWS Route53

Create an account with AWS. Use Route53 to buy a domain name. You can usually find a cheap name with an unpopular suffix. 
For example, at the time of this writing, .click domains are $3/year. 

### Option 2: Namecheap

Visit NameCheap to purchase a domain name. You will need to create an account there. A domain name may cost you about $10 for a year. 
For example, you may be able to purchase a domain name that uses your real name, such as emmasmith.org. 
You can pick whatever you like. Navigate to "Configure Namecheap DNS" if you want to use NameCheap.

## Configure your DNS 
### Configure your DNS Using Route53
1. Log in to AWS using your AWS account. 

Follow these instructions to [purchase and register a domain](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-register.html#domain-register-procedure). 
After you purchase your domain name you need to respond to an email that the naming authority will send to you. 
After that you need to wait until AWS recognizes your purchase and it creates a Hosted Zone for you domain. 
Then you are ready to set up your DNS. This is also done with the Routee53 service.

2. Navigate to Hosted Zones and select the zone that matches the host name you just purchased.
3. Add a new A record and leave the name field empty for the host, and put the IP address of your Digital Ocean machine in the value field. This will be the DNS record that maps your root hostname to your server. For example, if the hostname your purchased was cs260.click then https://cs260.click would now go to your server. Save this new record.
4. Click "Add new record". Choose "A record" and enter "*" for the host, and the IP address of your Digital Ocean machine in the value field. This will map all of your subdomains to your server. For example, if the hostname your purchased was cs260.click then https://lab1.cs260.click would now go to your server. You are going to create several subdomains throughout the class. Save this new record.
 
 Congratulations! You've now configured your own Domain! Skip Configure NameCheap DNS and 
 navigate go directly to "Understanding NGINX configuration" to continue reading.
 
### Configure your DNS using Namecheap

Do not follow these steps if you are already set up DNS using AWS Route53. You only need to setup your DNS records in one place.

After you purchase your domain name, you need to [set it up](https://www.namecheap.com/support/knowledgebase/article.aspx/434/2237/how-do-i-set-up-host-records-for-a-domain/) 
so that anyone who uses DNS to look up your domain name will retrieve the IP address of your Digital Ocean server.

To do this, the first step is to add a new DNS record. In Name Cheap, navigate to your domain and click "Advanced DNS".

You need to add two DNS records and delete the two default records that are there. (The defaults are a CNAME and a URL redirect that shows a parked web page).

1. Click "Add new record". Choose "A record" and enter "@" for the host, the IP address of your Digital Ocean machine, and "20 minutes" for the TTL. Save this.
2. Click "Add new record". Choose "A record" and enter "*" for the host, the IP address of your Digital Ocean machine, and "20 minutes" for the TTL. Save this.
3. Delete the other two records. 

When you have added the records successfully your "Advanced DNS" tab will contain records that look like this:

![](namecheaprecords.png)

It may take some time for these changes to be updated throughout the Internet (15 to 30 minutes), but after some time you should be able to browse to your website using the domain name you purchased and any subdomains. For example, if you try the following domains, they should go to the same site:

- emmasmith.org
- lab1.emmasmith.org
- cp1.emmasmith.org

Congratulations! You've now configured your own Domain! Navigate to "Understanding NGINX configuration" to continue reading.

