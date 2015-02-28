# Camel Fabric QuickStart

This example shows how to use the Fabric Camel component.

This example is implemented using Java code with CDI injected resources. The source code is provided in the following two java files:
- `src/main/java/io/fabric8/quickstarts/camelfabric/client/MyRoute.java`, which can be viewed from [github](https://github.com/fabric8io/fabric8/blob/master/quickstarts/java/camel-fabric/camel-fabric-client/src/main/java/io/fabric8/quickstarts/camelfabric/client/MyRoute.java) and
- `src/main/java/io/fabric8/quickstarts/camelfabric/consumer/MyRoute.java`, which can be viewed from [github](https://github.com/fabric8io/fabric8/blob/master/quickstarts/java/camel-fabric/camel-fabric-consumer/src/main/java/io/fabric8/quickstarts/camelfabric/consumer/MyRoute.java).


On the client side, this example uses a timer to create messages every 5 seconds and sends the message to the `fabric:MyFabricEndPoint`.
On the consumer side, it exposes a jetty endpoint, which is registered under `fabric:MyFabricEndPoint`.


### Building this example

The example comes as source code and pre-built binaries with the fabric8 distribution. 

To try the example you do not need to build from source first. Although building from source allows you to modify the source code, and re-deploy the changes to fabric. See more details on the fabric8 website about the [developer workflow](http://fabric8.io/gitbook/developer.html).

To build from the source code:

1. Change your working directory to `quickstarts/java/camel-fabric` directory.
1. Run `mvn clean install` to build the quickstart.

After building from the source code, you can upload the changes to the fabric container:

1. It is assumed that you have already created a fabric and are logged into a container called `root`.
1. Change your working directory to `quickstarts/java/camel-cdi` directory.
1. Run `mvn fabric8:deploy` to upload the quickstart to the fabric container.

If you run the `fabric:deploy` command for the first then, it will ask you for the username and password to login the fabric container.
And then store this information in the local Maven settings file. You can find more details about this on the fabric8 website about the [Maven Plugin](http://fabric8.io/gitbook/mavenPlugin.html).


## How to run this example

The following information is divded into three sections, whether you are using the command line shell in fabric, or using the web console, or run the example from the source code.

### Using the command line shell

You can deploy and run this example at the console command line, as follows:

1. It is assumed that you have already created a fabric and are logged into a container called `root`.
1. Create a new child container and deploy the `quickstarts-java-camel.cdi` profile in a single step, by entering the
 following command at the console:

        fabric:container-create-child --profile quickstarts-java-camel.cdi root mychild

1. Wait for the new child container, `mychild`, to start up. Use the `fabric:container-list` command to check the status of the `mychild` container and wait until the `[provision status]` is shown as `success`.


### Using the web console

You can deploy and run this example from the web console, as follows

1. It is assumed that you have already created a fabric and are logged into a container called `root`.
1. Login the web console
1. Click the Wiki button in the navigation bar
1. Select `quickstarts` --> `java` --> `camel.cdi`
1. Click the `New` button in the top right corner
1. In the Create New Container page, enter `mychild` in the Container Name field, and click the *Create and start container* button

### From the source code

Follow the instructions from the _Building this example_ section, and after you have built the source code run the following command:

1. Run `mvn camel:run` to run the example as a standalone Spring based Camel application.

Running outside fabric means that you do not have the fabric web console or fabric server to manage the application. You may want to use `mvn camel:run` during development and to quickly try your code changes.


## How to try this example

The following information is divded into two sections, whether you are using the command line shell in fabric, or using the web console

## Undeploy this example

The following information is divded into two sections, whether you are using the command line shell in fabric, or using the web console


### Using the web console

To stop and undeploy the example in fabric8:

1. In the web console, click the *Runtime* button in the navigation bar.
1. Select the `mychild` container in the *Containers* list, and click the *Stop* button in the top right corner
