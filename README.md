# Zammad Connector for Camunda 8

## Overview

The **Zammad Connector** enables Camunda 8 process automation to seamlessly interact with Zammad for managing support operations. It allows BPMN workflows to create, retrieve, update, and delete support tickets, as well as search for and create users directly from Camunda without implementing custom integration logic.

The connector can be used within Camunda 8 processes by configuring the required operation, authentication, and input parameters in the connector task. This enables organizations to automate customer support workflows such as incident management, service requests, dispute handling, customer onboarding, help desk ticketing, and case management as part of their business processes.


---

# Features

The connector supports the following operations:

## Ticket Operations

* Create Ticket
* Get Ticket
* Update Ticket
* Delete Ticket

## User Operations

* Search User
* Create User

---
## Connector UI
<img width="938" height="465" alt="image" src="https://github.com/user-attachments/assets/9b3a7008-e86f-4cf5-8612-cdc879e36d50" />


---

# Installation

## Prerequisites

Before setting up the Zammad Connector, ensure the following are installed:

* Docker Desktop
* Git
* Camunda 8 (Self-Managed or SaaS)
* Camunda Modeler 5.x or later

## Step 1: Set Up a Local Zammad Instance

Clone the official Zammad Docker Compose repository:

```bash
git clone https://github.com/zammad/zammad-docker-compose.git
```

> **Note:** Keep your local repository up to date by running:


Alternatively, you can download the latest Docker Compose files from the Zammad releases page.

## Step 2: Configure the Environment (Optional)

The default Docker Compose configuration is suitable for most development environments. If required, customize the deployment by modifying the provided environment variables or using one of the available Docker Compose scenarios based on your requirements.

## Step 3: Start Zammad

Navigate to the cloned repository and start the Docker containers:

```bash
cd zammad-docker-compose
docker compose up -d
```

The initial startup may take several minutes while Docker downloads the required images and initializes the services.

## Step 4: Access Zammad

Once all containers are running, open your browser and navigate to:

```text
http://localhost:8080
```

Complete the initial Zammad setup wizard by creating the administrator account and configuring the basic system settings.

## Step 5: Generate an API Token

1. Sign in to Zammad using the administrator account.
2. Open **Profile**.
3. Navigate to **Token Access**.
4. Create a new API Token.
5. Copy the generated token.

This API token will be used to authenticate requests from the Camunda 8 Zammad Connector.

---

## Setup Guide


### Setting Up in Saas/Self managed Environment:
1.	Navigate to Camunda SaaS.
2.	Upload the connector template from https://github.com/ak-chaudhari423/zammad-connector/blob/main/connector-template/zammad-connector.json or download it from marketplace.

---



## Using in Desktop Modeler

1. Go to:

```
Camunda Modeler → resources → element-templates
```

2. Paste the downloaded **Zammad Connector Template JSON**

3. Restart Modeler
   
```
# Operations

## Create Ticket

Creates a new support ticket.

### Required Inputs

| Property | Description     |
| -------- | --------------- |
| Domain   | Zammad Base URL |
| Customer | Customer Email  |
| Group    | Ticket Group    |
| Title    | Ticket Title    |
| State    | Ticket State    |
| Priority | Ticket Priority |
| Subject  | Article Subject |
| Body     | Article Body    |


