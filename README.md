# Cysic Verifier Node Setup

This guide will walk you through the process of setting up and running a **Cysic Verifier Node**. The Cysic Verifier Node is responsible for ensuring the integrity and accuracy of blockchain data by validating blocks and transactions.

### Table of Contents

1. [Overview](#overview)
2. [System Requirements](#system-requirements)
3. [Installation](#installation)
4. [Configuration](#configuration)
5. [Running the Verifier Node](#running-the-verifier-node)
6. [Monitoring and Logs](#monitoring-and-logs)
7. [Troubleshooting](#troubleshooting)
8. [Contributing](#contributing)
9. [License](#license)

---

## 1. Overview

The Cysic Verifier Node is a key component in the Cysic ecosystem, allowing you to verify the blockchain’s integrity. By running a Verifier Node, you actively participate in the network by validating blocks and ensuring data accuracy.

This guide will help you set up the node, configure the environment, and monitor its performance.

---

## 2. System Requirements

Before starting the installation, make sure your environment meets the following system requirements:

### **Hardware Requirements:**

* **CPU**: Minimum 2 cores
* **RAM**: At least 4GB
* **Disk**: SSD recommended (20GB free space minimum)
* **Internet**: A stable internet connection (at least 1Mbps download/upload)

### **Software Requirements:**

* **Operating System**: Linux (Ubuntu recommended), macOS, or Windows (with WSL)
* **Node.js**: Version 14.x or higher
* **npm**: Version 6.x or higher
* **Docker**: (Optional for containerized environment, recommended for production)
* **Git**: For cloning the repository
* **API Key**: Required for interacting with the Cysic blockchain network (available via the Cysic Portal)

---

## 3. Installation

### Clone the Repository

First, clone the Cysic Verifier Node repository to your local machine:

```bash
git clone https://github.com/yourusername/cysic-verifier-node.git
cd cysic-verifier-node
```

### Install Dependencies

You can install the necessary dependencies by running:

```bash
npm install
```

Alternatively, if you prefer `yarn`:

```bash
yarn install
```

### Docker Setup (Optional)

If you prefer to run the node inside a Docker container, follow these steps to set it up:

1. Ensure Docker is installed and running.

2. Build the Docker image for the Verifier Node:

   ```bash
   docker build -t cysic-verifier .
   ```

3. Run the Docker container:

   ```bash
   docker run -d --name cysic-verifier -p 8080:8080 cysic-verifier
   ```

---

## 4. Configuration

### Configure the Verifier Node

After installing the dependencies, configure the Cysic Verifier Node by editing the `config.json` file located in the `config/` folder.

Here are the configuration options you can adjust:

* **network**: Specify the blockchain network (`mainnet`, `testnet`, `devnet`).
* **port**: The port on which the verifier node will run (default is `8080`).
* **apiKey**: Your Cysic API key (required for connecting to the network).
* **syncInterval**: The interval (in seconds) to sync with the blockchain (default is `300` seconds).

### Example `config.json`

```json
{
  "network": "mainnet",
  "port": 8080,
  "apiKey": "your-api-key-here",
  "syncInterval": 300
}
```

Ensure that the **API key** is properly set, as this is required to interact with the blockchain network.

---

## 5. Running the Verifier Node

### Run Without Docker

To run the Cysic Verifier Node directly on your machine, execute the following command:

```bash
npm start
```

This will launch the Verifier Node and start synchronizing with the blockchain.

### Run With Docker

If you're using Docker, start the container with:

```bash
docker start cysic-verifier
```

The node will now begin verifying blocks and transactions on the selected network.

---

### Running the Verifier Node with Setup Script

If you prefer an automated setup, you can run the following commands to quickly install and configure the Verifier Node.

1. Replace the `0x-Fill-in-your-reward-address-here` with your actual reward address in the command below:

   ```bash
   curl -L https://github.com/cysic-labs/cysic-phase3/releases/download/v1.0.0/setup_linux.sh > ~/setup_linux.sh && bash ~/setup_linux.sh 0x-Fill-in-your-reward-address-here
   ```

2. Navigate to the directory containing the Verifier Node and start the node:

   ```bash
   cd ~/cysic-verifier/ && bash start.sh
   ```

This script will automatically configure and start the Cysic Verifier Node for you.

---

## 6. Monitoring and Logs

Once your Verifier Node is running, you can monitor its status and view logs.

### View Logs

To view the logs for the Verifier Node, run:

```bash
npm run logs
```

This command will display the logs, showing block verification status, transaction checks, and any errors that may occur.

### Check Sync Status

You can check the node's synchronization status by visiting the following URL:

* **Local**: `http://localhost:8080`

This page will provide information on the current state of the node’s synchronization with the blockchain.

---

## 7. Troubleshooting

If you run into issues while setting up or running the Verifier Node, here are some common troubleshooting steps:

* **Missing Dependencies**: Ensure you ran `npm install` or `yarn install` to install all necessary dependencies.
* **Configuration Issues**: Double-check the `config.json` file for any mistakes, particularly the network settings and API key.
* **Port Blocked**: If you’re unable to connect to the Verifier Node, ensure the port (default `8080`) is open and not blocked by a firewall or other services.
* **Sync Issues**: If the node is not syncing with the blockchain, restart the node and check the logs for any errors related to the connection.

If the problem persists, consult the Cysic documentation or reach out to support.

---

## 8. Contributing

We welcome contributions from the community! If you'd like to improve the project, please follow these steps to contribute:

1. **Fork the repository**.
2. **Create a new branch** (`git checkout -b feature/your-feature`).
3. **Make your changes** and test thoroughly.
4. **Commit your changes** (`git commit -am 'Add new feature'`).
5. **Push to your forked repository** (`git push origin feature/your-feature`).
6. **Submit a pull request**.

Please ensure your changes are well-documented and include tests if applicable.

---

## 9. License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

---

### Additional Resources

For more details on the Cysic Verifier Node, including advanced configurations and troubleshooting, visit the official [Cysic Documentation](https://docs.cysic.xyz).

---

