<pre>
The acctinfo script can provide you lots of information for an account on your 
cPanel server.  

This includes any addon domains, sub domains, parked domains, databases, 
SSL Certificates.  It will list the package the account has, whether it has a 
dedicated or is using the servers shared IP address, when the user last logged in, 
whether or not they are a reseller, how long they have been a customer, etc...

It also tells you what IP address the DNS currently resolves to. You can pass it
either a cPanel user name or a domain name.  (Any domain name, even parked or addons).

It can come in very handy when you need to quickly find out information on a
particular account or domain.

You can either download it to your /root/bin folder or you can run it from the 
command line.  I created an alias in my .bashrc file.

alias acctinfo="perl <(curl -s https://raw.githubusercontent.com/cPanelPeter/acctinfo/master/acctinfo)"

So you can call it as follows: 

# acctinfo --listdbs cptestdomain.net

or by username

# acctinfo --listdbs cptestdo

The following options are available: 

--listdbs cpanel.net
    Lists any MySQL databases (and their sizes) for cpanel.net

--listsubs cptestdo
    Lists all sub domains under the cptestdo user name.

--listaddons cptestdomain.net
    Lists all addon domains under the cptestdomain.net domain name.

--listparked cptestdomain.net
    Lists all parked domains under the cptestdomain.net domain name.

--listreseller cptestdo
    Lists reseller information and domains under the cptestdo user name.

--listssls cptestdomain.net
    Lists any SSL's under the cptestdomain.net domain name.

</pre>


