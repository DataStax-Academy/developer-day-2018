## Enable Workload

Certain Developer Day notebooks make use of various features in DataStax Enterprise, which need to be specifically enabled.

### Using the binary tarball

These features can be enabled with command-line flags when starting up DataStax Enterprise. This includes:

`-s` Search<br>
`-k` Analytics<br>
`-g` Graph

An example of starting up DSE with the Search workload:
```
bin/dse cassandra -s
```

You can also set multiple flags together. For example, the following enables all 3 features:
```
bin/dse cassandra -s -k -g
```

### Using the package install

The package install uses a property file located in `/etc/default/dse` to determine which features to start DataStax Enterprise with.

The beginning of the file should look something like this:
```
# NOTICE: See also /etc/dse/cassandra/cassandra-env.sh

# EXTRA_CLASSPATH provides the means to extend Cassandra's classpath with
# additional libraries.  It is formatted as a colon-delimited list of
# class directories and/or jar files.  For example, to enable the
# JMX-to-web bridge install libmx4j-java and uncomment the following.
#EXTRA_CLASSPATH="/usr/share/java/mx4j-tools.jar"

# Enable the DSE Graph service on this node
GRAPH_ENABLED=0

# Start the node in DSE Search mode
SOLR_ENABLED=0

# Start the node in Spark mode
SPARK_ENABLED=0
```

Change the desired feature from 0 to 1 in order to enable it. Afterwards, run `sudo service dse restart` to have the changes take effect.
