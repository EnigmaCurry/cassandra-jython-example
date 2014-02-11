## Cassandra Jython Example

Just a simple Jython project that connects to Cassandra and runs a few queries utilizing the DataStax Java Driver.

### Setup

Prerequisites :

 * [ant](https://ant.apache.org)
 * [ivy](https://ant.apache.org/ivy/)
 * A running Cassandra (2.0+) cluster on localhost. For testing, the easiest way is with [ccm](https://github.com/pcmanus/ccm)
 * cassandra-driver-core jar file, which can be found in the cassandra source [repo](https://github.com/apache/cassandra/tree/trunk/tools/lib)
 * Jython standalone jar, found on the download page [here](http://www.jython.org/downloads.html)

You need to give ant some extra permissions in order to run the test. Edit $JAVA_HOME/jre/lib/security/java.policy and add:

    grant {
      ....

      permission javax.management.MBeanTrustPermission "register"; 

      ....
    }

If you are using java from a package install and not using $JAVA_HOME you may need to manually find and edit java.policy as above.

After installing ivy, you may need to copy ivy.jar to where ant can see it, such as: ~/.ant/lib/ivy.jar .

Drop the cassandra-driver-core jar and Jython standalone jars into a jars/ directory within your checkout of this source.

Update the build.xml file to correctly reference the cassandra-driver-core and Jython standalone jars by name.

Then you should just be able to run `ant run` in the root of the checkout to download all the dependencies and run paging_example.py
