# Jboss-zabbix

This is a Zabbix(4.0+) template and scripts to monitor jboss jvm stats.
Data collected via wget http queries to a managment port(default 9990) of a jboss instance.
A management user(zabbix) required to access management realm. Create management user with this command:
<pre>$JBOSS_HOME/bin/add-user.sh -s -u zabbix -p PASSWORD</pre>

In template change this macro values to support your needs:</br>
<pre>
{$DATA_DISCOVERER} /PATH/TO/jboss_jvm_discovery
{$DATA_COLLECTOR}  /PATH/TO/jboss_jvm_data
{$MANAGMENT_PASS}  PASSWORD
{$MANAGMENT_USER}  zabbix
{$MANAGMENT_PORT}  9990
</pre>

Collected items:</br>
Application active sessions</br>
Application sessions created</br>

Class count loaded</br>
Class count total loaded</br>
Class count unloaded</br>

Data source available count</br>
Data source in use count</br>
Data source max wait count</br>

JVM Uptime</br>
JVM VM-Name</br>
JVM VM-Vendor</br>
JVM VM-Version</br>

Memory Heap committed</br>
Memory Heap init</br>
Memory Heap max</br>
Memory Heap used</br>

Memory Non heap committed</br>
Memory Non heap init</br>
Memory Non heap used</br>

Thread count</br>
Thread count daemon</br>
Thread count peak</br>

Thread count total started</br>

<a href="https://t.me/sshtobash"><img src="https://telegram.org/img/website_icon.svg" width="21"></a>
[![Twitter Follow](https://img.shields.io/twitter/follow/Vaniacer?style=social)](https://twitter.com/Vaniacer)
[![paypal](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://paypal.me/sshto?locale.x=en_US) <sup>Don't hold yourself, buy me a beer)</sup>

There are two discovery rules for garbage collectors(GC) and memory pools(MP).
For each discovered GC this items will be created: collection-count and collection-time.
And for MP: usage committed, usage init, usage max, usage used.
Some graphs and triggers added.
