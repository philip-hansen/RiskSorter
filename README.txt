HOW TO USE

List.txt
This file contains the list of companies to get data for.
Each line represents 1 company and is in formatted by
"CIK TICKER", where CIK is the 10-digit (including leading 
zeroes if necessary) CIK of the company
and [TICKER] is the ticker. The ticker is (technically) optional and 
is only used for convenience purposes when reading the output; a 
wrong ticker will not change the program operation.

Running
Either run the "run.ps1" which will run the program and print the
output to a file called "risks-(date).txt" (you may need to right
click and press 'Run with Powershell'), or open a powershell
session, navigate to the directory containing the program,
and either type ".\RiskSorter" to run it (which will print output
to the window), or ".\RiskSorter >> (filename).txt" to write to a file
with a custom name.

The SEC is pretty particular about how their data is accessed. In
particular, only 10 requests per second are allowed, so I have
introduced an artificial delay between web requests to reduce the load
on their servers (each company requires 3 web requests). This limit
from the SEC is subject to change. With the current configuration,
the program should take about 1 second per company in the list.

They are also (sort of) able to track who is sending the requests
and do kick out abusers, so if there is an authorization error
or if all companies suddenly start to fail to get data (unlikely 
but not impossible), I will need to change some configurations in 
the program to get it working again.