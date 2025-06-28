# Week 1 

## Challenge 1 [Try Hack Me]

### Task 13 ['Tis the season for log chopping!]

#### Challenge Description

To take revenge for the company demoting him to regional manager during the acquisition, Tracy McGreedy installed the CrypTOYminer, a malware he downloaded from the dark web, on all workstations and servers. Even more worrying and unknown to McGreedy, this malware includes a data-stealing functionality, which the malware author benefits from!

The malware has been executed, and now, a lot of unusual traffic is being generated. What's more, a large bandwidth of data is seen to be leaving the network.

Forensic McBlue assembles a team to analyse the proxy logs and understand the suspicious network traffic.

#### WriteUp

Following are the quetions asked in this task:-

How many unique IP addresses are connected to the proxy server?

Its simple we just need to use cut with uniq and wc.
```
cut -d ' ' -f 1 /path/to/logfile | sort | uniq | wc -l

```



