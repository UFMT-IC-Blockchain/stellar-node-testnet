# Stellar Watcher Node (Testnet)

This configuration enables the execution of a Stellar node in watcher mode, a non-validator setup, utilizing the Testnet network environment. The primary objective is to provide access to the Horizon API and Core for data queries and transaction submission.

### Components and Ports

The infrastructure relies on the `stellar/quickstart` image. The following ports map to the host:

* **8000**: Horizon API interface; used for network interactions.
* **11625**: Stellar Core P2P protocol; essential for inter-node communication.
* **11626**: Core information via HTTP; provides internal node status.
* **5432**: PostgreSQL database access; restricted to the local address (127.0.0.1).

### Volume and Log Configuration

The `./stellar_data` local directory centralizes persistence. The configuration maps specific paths for logs, facilitating integration with monitoring systems such as Zabbix:

1.  **/opt/stellar**: General data and configurations.
2.  **/var/log/stellar-core**: Core activity logs.
3.  **/var/log/horizon**: Ingestion API logs.
4.  **/var/log/postgresql**: Database logs.

---
