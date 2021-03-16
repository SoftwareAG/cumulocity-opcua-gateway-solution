# OPC Server and Gateway

This solution creates a sample OPCServer including the required gateway to connect the OPC server to Cumulocity.
See as well: [OPC UA Agent Cumulocity](https://cumulocity.com/guides/10.7.0-beta/protocol-integration/opcua)
The registration data are stored in the ./data directory that are mapped as a volume to the docker service gateway. And thus still exits after a restart

# Edit application-tenant.yaml and adapt the baseUrl and the tenantId:

    C8Y:
        baseUrl: https://TENANT_URL
    gateway:
        bootstrap:
            tenantId: TENANT_ID
        identifier: Sample_Gateway_Device
        name: Customer Gateway
        db:

The start the solution by running:

    docker-compose up -d --no-deps --build

# Register opcserver with: opc.tcp://opcserver:4840

![Register OPC server](./doc/Register.png)

# Browse OPC tree

Once the gateway scanned the OPCTree you can view its content:

![Browse OPC tree](./doc/OPC_Tree.png)
