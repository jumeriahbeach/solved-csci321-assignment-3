Download Link: https://assignmentchef.com/product/solved-csci321-assignment-3
<br>
<h2>The Assignment</h2>

You’ll find a <strong>resolve.py</strong> file in your repo. This file contains code that approximates the functionality of the host program. The program takes a domain name, and returns a summary of DNS information about the domain. For example, given the domain “<strong>yahoo.com</strong>”, host returns the “<strong>A</strong>”, “<strong>AAAA</strong>” and “<strong>MX</strong>” records for the domain.

You can test this out by running the resolve.py command as so:

<strong>python resolve.py yahoo.com. </strong>

<strong>resolve.py</strong> currently queries a DNS server (<strong>8.8.8.8</strong>) to find information about domains. That DNS server handles the recursive part of DNS for you (i.e. <strong>8.8.8.8 </strong>by default doesn’t know where to find <strong>yahoo.com.</strong>, so it asks a root server, and the root server tells <strong>8.8.8.8</strong> where to find information about .com, so then <strong>8.8.8.8</strong> asks the new server where to find <strong>yahoo.com.</strong>, etc.)

Your task in this assignment is to implement this recursive functionality on your own. When your version of <strong>resolve.py</strong> is run, it will not query <strong>8.8.8.8</strong> (or any other recursive resolver). Your <strong>resolve.py</strong> will query a root server itself, as well as performing any further needed queries.

The IP addresses of the root servers are hard coded into the <strong>resolve.py</strong> in the global <strong>ROOT_SERVERS</strong> list. Your program should start by querying one of these servers. A very good first step in your solution will be to find where <strong>8.8.8.8 </strong>is in the code currently, and make sure you instead query one of the root servers.




Using the responses from what you get from the root severs, you will then ask one of the TLD servers, and so on and so on. The base case of your recursive function will be when you have received the actual <strong>A</strong>, <strong>AAA</strong>, and <strong>MX</strong> records for a given domain.




<h2>Additional Implementation Instructions</h2>

<ul>

 <li>Your y a timeout value of 3 seconds for all queries. Any request taking more than 3 seconds to respond should be treated as non-responsive.</li>

 <li>Like the demo in for DNS in class, you can pick a server randomly from the list of servers.</li>

 <li>You should exhaustively try all available servers when trying to answer a query. For example, if a request to a root server gives you 13 servers for the “<strong>.com</strong>” TLD, you should try each of those 13 servers before giving up</li>

 <li>If you receive an error or non-response from a server, you should not retry the server.</li>

 <li>Only query servers over IPv4. You should not query servers over IPv6 when trying to resolve domains.</li>

</ul>




<strong> </strong>