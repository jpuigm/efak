efak is a set of distributed processes to build financial application based
on the iso8583 protocol.

efak is composed of three main parts

## Interfaces ##

Interfaces handle specific iso8583 implementation that you can configure to match your requirement.
In the configuration file you can specify the iso fields and messages each single interface needs to implement.
The interface processes handle message parsing/testing against
the configured specification and logging of transactions.

## Lines ##

Lines provide connection capability to remote iso8583 interfaces you have to connect to.
Lines can be deployed on different nodes for redundancy and
load balancing while being connected to a single interface.

## Transactions ##

Every incoming message is handled within an erlang process, common transaction flow is implemented in the iso\_transaction behaviour.
The transaction\_mgr collects messages coming from the interfaces and starts the transaction processes.

The included bg\_example application demonstrates how to configure and use efak.