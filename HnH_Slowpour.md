# HnH Slowpour WriteUp

## Network Traffic Analysis
In this challenge the main keyword was the PCAP file just open this file in wirehshark and check for ftp the banner is at the top and thats the flag.

## Misc
This challenge was thier to just to make sure everybody reads the rules just be on that page for sometime and it will automatically give you the flag in a popup.

## OSINT & Recon

I felt this challenge more like a web one we need to just go inspect and check the files i searched with the keyword "HnH{" and got the flag.

## Reverse Engineering

On opening the js file its clear that first we need to reverse the base64 after doing that we can see that "var hTierMem = Buffer.from( "SG5Ie09iZnVzY2F0aW9uSXNBbHNvTm90RW5jcnlwdGlvbn0=","base64");" this decodes to HnH{ObfuscationIsAlsoNotEncryption} and this is the flag .
