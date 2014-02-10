## Jython Cassandra Example

Just a simple Jython project that connects to Cassandra and runs a few queries utilizing the DataStax Java Driver.

### Setup

Prerequisites :

 * [ant](https://ant.apache.org)
 * [ivy](https://ant.apache.org/ivy/)

You need to give ant some extra permissions in order to run the test. Edit $JAVA_HOME/jre/lib/security/java.policy and add:

    grant {
      ....

      permission javax.management.MBeanTrustPermission "register"; 

      ....
    }


Then you should just be able to run `ant run` in the root of the checkout to download all the dependencies and run paging_example.py
