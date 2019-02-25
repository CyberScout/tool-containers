![RabbitMQ logo](rabbitmq128.png)

# RabbitMQ Server

This set of scripts launches the latest 3.x version of RabbitMQ Server within a Docker container. The management
interface is available.

## Running the RabbitMQ server

To run the RabbitMQ container, open a terminal and navigate to the location of the script.

```
~/src/tool-containers/rabbitmq$ ./rabbitmq
```

RabbitMQ will be listening on the default port, 5672. The management interface will be accessible on port 15672.

There is no persistent volume used, so queued messages will be lost when the server is shutdown.

Use the file `enabled_plugins` to control which plugins are enabled. Add or remove the desired plugins from the list.
Changes to this file _might_ be picked up on-the-fly (no restart needed).
