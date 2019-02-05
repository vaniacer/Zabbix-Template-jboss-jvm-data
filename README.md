# Jboss-zabbix

This is a Zabbix template to monitor jboss jvm stats.</br>
Data collected via wget http queries to a managment port(default 9990).</b>

You need to create management user(zabbix) in jboss.
<pre>$JBOSS_HOME/bin/add-user.sh -s -u zabbix -p PASSWORD</pre>

In template change this macro values to support your needs:<br>
<pre>
{$DATA_COLLECTOR}  /PATH/TO/jboss_jvm_data
{$DATA_DISCOVERER} /PATH/TO/jboss_jvm_discovery
{$MANAGMENT_PASS}  PASSWORD
{$MANAGMENT_PORT}  9990
{$MANAGMENT_USER}  zabbix
</pre>
