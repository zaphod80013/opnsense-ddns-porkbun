# opnsense-ddns-porkbun

## Introduction

While evaluating Opnsense as a replacement for Pfsense I discovered it doesn't have a dynamic DNS plug-in for Porkbun, my domain registrar, I don't know if this is an official plug-in that I missed or not so I rolled my own using other plug-ins and the Pfsense php client as a template. I not going to claim it is correct or the best solution possible; for example it can't handle multiple entries for the same sub-domain and it's not tested on the root domain. Also, unlike Pfsense, it does not update the status in the DDNS dashboard widget when a WAN gateway goes offline (I don't know if this is a weakness in my code or the underlying Opnsense architecture). The plug-in works for me updating both IPV4 & IPV6 addresses correctly and it handles mapping the same IP address to multiple sub-domains which were my use-cases.

I only had Opnsense installed for a week because it has the same issues with network prefix translation I was seeing with pfsense and while there are some aspects of the Dashboard that I like I still prefer the pfsense dashboard (for the ability to collapse and configure widgets) so I'll be sticking to pfsense for now and not spending any time on this plugin.

If somebody wants to clean this up and roll it into Opnsense as an official plug-in feel free to do so. 

## Installation

Simply copy Porkbun.py to **/usr/local/opnsense/scripts/ddclient/lib/account/porkbun.py** and make it executable.







