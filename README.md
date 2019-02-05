# Jboss-zabbix

This is a Zabbix template to monitor jboss jvm stats.
Data collected via wget http queries to a managment port of jboss instance(default 9990).
So you have to create a management user(zabbix) in jboss for access to management realm.
<pre>$JBOSS_HOME/bin/add-user.sh -s -u zabbix -p PASSWORD</pre>

In template change this macro values to support your needs:</br>
<pre>
{$DATA_COLLECTOR}  /PATH/TO/jboss_jvm_data
{$DATA_DISCOVERER} /PATH/TO/jboss_jvm_discovery
{$MANAGMENT_PASS}  PASSWORD
{$MANAGMENT_PORT}  9990
{$MANAGMENT_USER}  zabbix
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

There are two discovery rules for garbage collectors(GC) and memory pools(MP).
For each GC then creates items: collection-count and collection-time.
And for MP: usage committed, usage init, usage max, usage used.
