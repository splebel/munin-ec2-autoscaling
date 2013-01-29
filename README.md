Munin EC2 Autoscaling plugin
============================

Prerequisites
-------------
- Auto Scaling Command Line Tool (http://aws.amazon.com/developertools/2535)
- Java JRE

Installation
------------
- Copy ec2_autoscaling_ to /usr/share/munin/plugins/
- Make a symlink of ec2_autoscaling_ to /etc/munin/plugins/ec2_autoscaling_MyAsGroup

Configuration
-------------
Here is a generic configuration, you may skip JAVA_HOME and AWS_AUTO_SCALING_HOME if they are already defined in your env
	[ec2_autoscaling_*]
	env.JAVA_HOME=
	env.AWS_AUTO_SCALING_HOME=
	env.AWS_ACCESS_KEY_ID=
	env.AWS_SECRET_ACCESS_KEY=

If you wish to have the results on a different host (like with snmp)
	[ec2_autoscaling_MyAsGroup]
	host_name MyHostName

And add an entry in munin.conf
	[MyHostName]
	address 127.0.0.1

You can test the configuration with the following
	munin-run ec2_autoscaling_MyAsGroup

