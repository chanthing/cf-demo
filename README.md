cf-demo
=======

A simple example of using the HD Service for Pivotal CF. Implements a simple REST endpoint to
list the files in HFS.

Setup/Deployment
----------------

The code assumes that there is an instance of the HD service named `hd-demo`. This can be changed
by editing the `service-name` attribute of the `hadoopConfiguration` bean in 
`src/main/resources/hadoop-context.xml`. The service name is also referenced in `manifest.yml`, and
would need to be changed there as well. 

1. `mvn clean package`
2. `cf api <url of CF api endpoint>`
3. `cf login`
4. `cf push` 

By default, this will push the app using the name in the manifest, cf-demo. If necessary, you 
can either change the name in the manifest, or specify a name for the push command.


Access
------

Once the app is deployed and running, you can access the app at

http://cf-demo.cfapps.yourdomain.com/ls

You can also specify path arguments, such as

http://cf-demo.cfapps.yourdomain.com/ls?path=/yarn




