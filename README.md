# OpenShift Wildfly Cartridge

This cartridge is running JBoss 7.2.0.Final

This cartridge is based on the JBoss AS cartridge found in OpenShift Origin [here](https://github.com/cwpenhale/openshift-jboss720-cartridge).  

Pretty much everything seems to be working fine, but it can still use some testing.  

If you find any issues, please log them in the [issues](https://github.com/developercorey/openshift-wildfly-cartridge/issues) section of the [github](https://github.com/developercorey/openshift-wildfly-cartridge) project.  

This cartridge will act very similarly to the jbossas-7 cartridge that you can create a gear with.  
You should be able to modify the code in the /src directory of the git repository, and do a git add, git commit, and git push and have it deployed as ROOT.war.  
You can also remove the pom.xml and /src directories and place a war file in the deployments directory and they should deploy like they do on JBoss AS 7  


You can build a gear using this cartridge with the following command:

	rhc app create jboss720 https://raw.github.com/developercorey/openshift-wildfly-cartridge/master/metadata/manifest.yml
	
It will take a few minutes to build, so be patient.

###Super Secret Hint (Don't tell anyone)

If you run the rhc port-forward command, you can access the WildFly management interface on port 9990  
A username and password is created when you install this cartridge.  
If you don't write it down, fear not, the following environment variables will contain them.  
$OPENSHIFT_WILDFLY_USERNAME  
$OPENSHIFT_WILDFLY_PASSWORD

	corey$ rhc port-forward wildfly
	Checking available ports ... done
	Forwarding ports ...

	To connect to a service running on OpenShift, use the Local address

	Service Local               OpenShift
	------- -------------- ---- -------------------
	java    127.0.0.1:8080  =>  127.13.118.129:8080
	java    127.0.0.1:9990  =>  127.13.118.129:9990
	java    127.0.0.1:9999  =>  127.13.118.129:9999
	
In this example you would visit 127.0.0.1:9990 to view the wildfly admin panel from your local computer.

## Thanks to the following:
@developercorey: https://github.com/developercorey


