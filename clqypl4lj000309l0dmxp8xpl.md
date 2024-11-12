---
title: "Try DragonflyDB on Spheron for a ~30x Cache Speed Boost!"
seoTitle: "Try DragonflyDB on Spheron for a ~30x Cache Speed Boost!"
seoDescription: "Follow the comprehensive guide to discover the power of combining DragonflyDB and Spheron to revolutionize your Nest.js API's performance by 30x Cache Speed"
datePublished: Thu Jan 04 2024 04:30:12 GMT+0000 (Coordinated Universal Time)
cuid: clqypl4lj000309l0dmxp8xpl
slug: try-dragonflydb-on-spheron-for-a-30x-cache-speed-boost
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1704210681121/31feb56b-8e96-41c3-86f8-79fd9ab5657e.png
tags: cache, blockchain, web3, decentralization, spheron

---

In modern web development, enhancing API performance is critical for delivering swift and scalable services. Leveraging caching solutions like Redis has been a standard practice, but with the emergence of [DragonflyDB](https://www.dragonflydb.io/), claiming a remarkable throughput of approximately 30 times more than Redis, there's an opportunity to explore and harness its potential.

This guide will explore how to supercharge your Nest.js API with DragonflyDB, a high-performance, [Redis-cli](https://docs.redis.com/latest/rs/references/cli-utilities/redis-cli/) compatible boasting up to 30x Redis's throughput in terms of QPS. You'll learn to set up DragonflyDB locally, deploy it on [Spheron](https://spheron.network/), and integrate it into a [Nest.js API](https://github.com/anataliocs/nestjs-dragonflydb-cache) as a caching layer.

## Getting Started with DragonflyDB

Before setting up DragonflyDB on Spheron, let's familiarize ourselves with the basics. DragonflyDB is a lightweight, in-memory data store built for modern application workloads. Fully compatible with Redis and Memcached APIs, Dragonfly requires no code changes to adapt. Unlike legacy in-memory datastores, Dragonfly delivers 25X more throughput, higher cache hit rates with lower tail latency, and can run on up to 80% less resources for the same sized workload. It offers a simple, efficient, cost-effective caching and session management solution. It's perfect for applications that require low latency, high throughput, and easy scaling.

To get started, we'll begin by running a DragonflyDB container locally using Docker. This will allow us to play around with the database and test its capabilities before deploying it to Spheron.

## Working with DragonflyDB in our Local Environment

First off, let’s get DragonflyDB running locally in a Docker container and test if we can use the **redis-cli** with it as a drop-in replacement.

### Install Docker Desktop for Mac

If you haven't already, please install Docker Desktop for Mac [from here](https://docs.docker.com/desktop/install/mac-install/). This will provide a convenient environment for running and managing Docker containers.

**Docker for Mac includes:**

* The Docker Daemon (dockerd) which manages containers and images and exposes the Docker API
    
* A GUI to track Docker images in the local repository, running and stopping Docker containers storage volumes, and lets you manage Docker settings.
    
* Docker CLI
    

![](https://lh7-us.googleusercontent.com/wZS3OrCYPNV5zmZ9-kG39kZuMdU7BrCnIayhblJpfk6MnBv9iDPx9s9Z2W7eQPWzOTKo8amRp5HSJoX5GpOr0i38TXdsGSlv0y2T3XaaATy1vjqEG3b_FHf4efYgxs96g_09PPtNJ6ASr-LHV8q9F_E align="left")

* Start up Docker
    
* Sign up for an account
    

### Run Docker Container Instance Locally

This command will pull down the Docker image to your local repository and then spin up the container based on the following parameters:

* **\-d** **:** *Runs in detached mode as a background process*
    
* **–ulimit memlock=-1** : *unbounded memlock value (Not recommended for prod)*
    
* **\-p** : *exposes port 6379 externally on the docker container, which maps to the same port in the container.  Pattern:  HOST:CONTAINER*
    

```dockerfile
docker run -d -p 6379:6379 --ulimit memlock=-1 docker.dragonflydb.io/dragonflydb/dragonfly
```

Check out the docs here:  [Docker run](https://docker-docs.uclv.cu/engine/reference/run/)

This command tells Docker to:

* Run the container in detached mode (-d flag).
    
* Map port 6379 on the host machine to port 6379 in the container (-p flag).
    
* Set the memory lock limit to unbounded (-u flag).
    

Once the container is up and running, you can verify its status using the ‘**docker ls’** command:

```dockerfile
docker ls
```

Which will display all currently running containers:

![](https://lh7-us.googleusercontent.com/CJQnlHpkpHjGU1TiwEtm5VOi5qERT1w2Iga5ciA1PJXb6f3YY__ocRI2vX7Nt61kmmWiooqSVLV3TzFx5LlPoDgvMQzzbF1O_TqBX_6riIWgg0w7S-rGRfZoFk8S07zFTrq8dnBMUQ49Nt8zVb32TLY align="left")

Or in the Docker Desktop GUI:

![](https://lh7-us.googleusercontent.com/I4hH1v0v3XvXpaZeIzbGOP_RpggkqsrYb8eI99RgCF379JflL6MU8dvzcMMvbiRX7Ct-WPD5zruqMs5VuVP13EcYPsBwAgCSn3DE7gp_lnXY7PfVA2f-eB8zvduPGz6qwpy0GC8zsBAlopF63l41NYs align="left")

### Install the Redis CLI

Dragonfly supports the Redis CLI command interface almost 1-to-1.

First off, use Brew to install the Redis CLI if you don’t already have it.

```dockerfile
brew install redis
```

For info on available commands:  [Redis CLI docs](https://redis.io/docs/connect/cli/)

### Connect to Dragonfly

Invoke the redis-cli to connect to the instance on the default port, 6379, running on [localhost](https://www.dragonflydb.io/).

```dockerfile
redis-cli
```

![](https://lh7-us.googleusercontent.com/XoXLtgIDDVzppoKnbz893sh__OpNCC-BrP2jlu_lIdS0id6OAfR7ptB0pL6sb-2cbtYf7UHjFG8orUbWrqlpZKGKhyfDFMXTBJkbNApyEenXi9U81nHy06e9k6FhdibuAt9fbsNQhwdtIk6UrnewE9w align="left")

### Persisting and Reading Primitive Data

DragonflyDB is an in-memory, key-value datastore just like Redis.

You can find the docs on the [Redis set command here](https://redis.io/commands/set/).

#### Getting and Setting a Simple String Value to a Key

Assign a new value to the defined key.  *Pattern:  SET key value*

```dockerfile
SET hello world
```

Now, retrieve the value associated with the "hello" key:

```dockerfile
GET hello
```

This will display the value linked to that key.

![](https://lh7-us.googleusercontent.com/ULEmlHw_6T0sYClc3mCiVaGnG3h47k77McwwCA_q51xQvzv818y0pov-_cRnZBtwqzjGIBnoh1AO0FB5xSnFnoFO5xxtSnAra1y5v4CaTtN2COtNFivYI0TtYmjST6sTPEogj4f42LK_6sg_k4k8tWQ align="left")

Calling SET again for the same key will overwrite the existing value.

You can add more keys and values:

```dockerfile
set hello:2 world2
set hello:3 world3
```

Retrieve all available keys:

```dockerfile
keys *
```

This will list all the currently available keys.

![](https://lh7-us.googleusercontent.com/F0greya3Yqr58BtVkmdmfDBiJ6FcJMCoxadaZu86UYD_rjIuGV2WzQrr8v-U-g2oJXajU0e8xAlkNYUR9e2tMrl2sv0iJMeAZvtft-Ef_mlmQOq2ZumtUi9L9Hm0Nc-lFA-OTJH3ys0Z0944M6d1KrI align="left")

### Storing Data Structures Values

DragonflyDB not only stores strings but also supports more complex data structures like JSON and lists. Here's an example of setting a JSON value to a key:

Check out the docs on [Dragonfly JSON here](https://www.dragonflydb.io/docs/category/json)

Here is an example of setting this JSON to the key etherprice:1

```dockerfile
JSON.SET etherprice:1 $ '{ "name" : "Ether", "symbol" : "ETH", "timestamp" : "2023-12-20T16:02:23.568Z", "price" : 2245.42 }'
```

Then, you can retrieve that JSON using the JSON.GET command:

```dockerfile
JSON.GET etherprice:1
```

This will return the value for that key:

![](https://lh7-us.googleusercontent.com/sjQSMQyLoxmGTMPldLZtKeOM5bGVAG3cuOcQ01GDGRZpvg56M8vC27CvBgJMcj17zX82VnAg_jtqqb861sOu1XaTUX_UF7Ve6PXphwsq5F-qHELUjZfkkT_CAd65NjPYGYsdT9ruEdf86j4jdg5qvtI align="left")

Which returns as a string with escaped quotes.

You can also parse the JSON using JSONPath expressions to get a specific value from the JSON:

![](https://lh7-us.googleusercontent.com/3b2Fy4bxZXag-fD7qImvstCBfQfnX2ZJR3CTNvGoQhcRxOUzkV39yavN0YMDUBbb8rnMJA7dYXpZSywJ9T2L-8uiJVo35kmv3iYhrF1AzOkI1RU-w-jjhIrKyHlIpXkFB5a-lzz13ze6K5dpoeynkvA align="left")

You can marshall the raw JSON string into a typed object using libraries in multiple languages.  Check out this spec for more detailed patterns on how [JSON is serialized in the wire protocol RESP](https://redis.io/docs/reference/protocol-spec/).

### Clean up Docker Artifacts

Now that we've finished playing with DragonflyDB let's clean up the Docker artifacts we created:

You can clear out the docker containers, images, and volumes afterward, if desired, using the following commands:

```dockerfile
docker container kill containerid
docker container prune
docker image rm imageid
```

## Run the Dragonfly Container on Spheron

Now, let’s get DragonflyDB running on Spheron.

### Step 1: Create a Free Spheron Network Account

1. Visit Spheron Network: [https://spheron.network/](https://www.dragonflydb.io/)
    
2. On the Spheron homepage, locate and click the "Free Trial" button.
    
3. You'll be directed to a login/signup page. Choose your preferred authentication method: Web2 (GitHub account, GitLab account, or Bitbucket account) or Web3 (Ethereum).
    
4. Follow the provided prompts to authenticate your chosen account securely. This step ensures safe access to the Spheron Network platform.
    
5. After successful authentication, you'll be guided to a confirmation page confirming the completion of your account setup.
    

### Step 2: Creating an Organization

1. Upon logging in, navigate to the "Compute" section using the dropdown on the top right corner.
    
2. You'll be prompted to create your organization's name, username, and Avatar. Add and click “Save.”
    
3. Next, you'll be taken to a new page. Click the "New Cluster" button.
    
4. **Select** Compute Type As: On-demand
    

### Step 3: Deploy the Dragonfly container on the Spheron Platform UI

1. Select “Import from Docker Registry” and enter the image and tag of the DragonflyDB Docker image from the GitHub Repository.  You can see more on the GitHub [Packages page for Dragonfly](https://github.com/dragonflydb/dragonfly/pkgs/container/dragonfly).
    
2. **Image:**  [ghcr.io/dragonflydb/dragonfly](https://www.dragonflydb.io/)
    
3. **Tag:** v1.13.0-ubuntu
    

![](https://lh7-us.googleusercontent.com/gKNnDfQtg4ae8elw5z9TriItTh-jyej2QH-WojNrh7caixPJ8QBiK1sbel8FGsI7t4MVVms9HD-kyjaiZDStULu-W6b0-zOwRu38_AvKX1wOTftoaD2oPWndVmF9zv4uefsgm2_j195fjsYzmaS4HhU align="left")

4\. Since it is a database, we need persistent storage, so toggle “Add Persistent Storage.” On and select a storage size:

Persistent storage will not be erased unless the instance is closed.

![](https://lh7-us.googleusercontent.com/-HpKWBeQEca4HXRFY7oCbRXe9cD4BBNeAvjpebBNPYyev5yFVXKvrtJ_TErln66XUxa4xnb24WRgBhv7k0K6jhPLdBhvtZwV7TGbmwxFL6VkIkLqhlKjCAf9Txr8Lrhkngs7l8tGBeBBCRYigFNcDxU align="left")

5\. Then, set the following values and select a size for Persistent Storage:

* Mount point: /data
    
* Type of Storage: SSD
    
* Port Mapping: 6379:Random Port
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1704707095865/ec5fb570-e987-4591-8964-513e60886ca9.png align="center")

**After your cluster deploys successfully:**

6\. Grab the Connection URL:

[provider.us-west.spheron.wiki:32333](https://www.dragonflydb.io/)

Then, navigate to that URL to test the deployment and view the Dragonfly status page.

![](https://lh7-us.googleusercontent.com/VUjcbbkJT3LNfls5GAKkRMO8lgRuQUvh0QJyX9CxiBl3VsAsmJM2MHvhzxldfTyxxGboQpmisWbPmcGeVXgLpRSR3A9VRaXbWxmtXT3_FXwxUJQi_z5lv_FwGQIpSdlTOysS6f2-QuBG8kF7hTAI1Zs align="left")

## Connect the Local Redis CLI to the Dragonfly Container Running on Spheron

**Connect to the container on Spheron:**

Get your hostname and port from Spheron, and then let’s connect to the instance using the Redis CLI:

```dockerfile
redis-cli -h provider.us-west.spheron.wiki -p 32333
```

You are now connected to the Dragonfly instance and can interact with the database!

## Running a Nest.js Typescript API using the DragonflyDB Instance on Spheron as a Cache

1\. Now, let’s pull down the [Nest.js reference app](https://github.com/anataliocs/nestjs-dragonflydb-cache) setup to query the OpenSea API and cache results in Dragonfly.  Clone this [repo](https://github.com/anataliocs/nestjs-dragonflydb-cache) locally:

```dockerfile
git clone git@github.com:anataliocs/nestjs-dragonflydb-cache.git
```

2\. Load up the project in your favorite IDE, and then let’s install dependencies:

```dockerfile
npm install
```

3\. Then, let’s set up your local config.  Create a .env file:

```dockerfile
touch .env
```

Then, we need to add the following parameters.  The REDIS\_HOST and REDIS\_PORT settings come from your deployed Spheron DragonflyDB instance.

4\. You will also need an OpenSea API key. If you need to provision a key, check out the OpenSea docs.

```dockerfile
REDIS_HOST=provider.us-west.spheron.wiki
REDIS_PORT=32333
OPENSEA_API_KEY=
```

5\. Now that our app is configured, let’s try running it!

```dockerfile
npm run start:dev
```

6\. After the app starts up, let’s try hitting the GET endpoint “[localhost:3000/opensea/proof-moonbirds”](https://www.dragonflydb.io/)

We can hit our API running on port 3000 by executing the following cURL command:

```dockerfile
curl --location 'localhost:3000/opensea/proof-moonbirds'
```

Alternatively, you can import that cURL command into a tool called Postman.  Postman is a GUI for managing and executing API calls.  You can [download Postman here](https://www.postman.com/downloads/)!

7\. After starting up Postman, you can generate an API request by using the import function.  Learn more about using the [import function in Postman Docs](https://learning.postman.com/docs/getting-started/importing-and-exporting/importing-curl-commands/). After importing the cURL command, you can click “Send” to execute the API call.  You should see the following JSON response:

![](https://lh7-us.googleusercontent.com/u_CmT66W4ky79BcBZavleOwy3ahF-XttWtR_gKFr8CHhQ-cFbbs0R0CFCkDH_Hz0uUgFIrFrib3wus4_MukVNHv-OV0pN6fbRyFZ17MOqc6aDqCUssQujF9kdwGaJ68oROAOuiihkkcPx7KS4pgF3SU align="left")

If you execute the API call again, it should be noticeably faster the second time!  This is because we are using a cached response from the DragonflyDB instance deployed on Spheron!

If we take a look at the Nest.js API logs, we can see the first API request had to reach out to the OpenSea API, but subsequent requests will be served from the cache.

![](https://lh7-us.googleusercontent.com/VWE6HL-haYeZjHeiFCmGEU1WYPywRn8CJ00_lLPKBFNvBn8OOJx2P5ZB8yce_tR4oaRbhOAuGH9IJLoXHUHW1Ai0jpZzhMHkl86YIM8aq8HFZydsU5TmfMlrkxI2x1bwETxHYhoeMMBQVu3qW9Nh7hk align="left")

This will allow you to improve the performance & scalability of your API while reducing the volume of requests that you have to make to OpenSea in case you are getting rate-limited.

8\. Now, let’s check in on our DragonflyDB instance.  Let’s connect to it again using the redis-cli with the following command:

```dockerfile
redis-cli -h provider.us-west.spheron.wiki -p 32333
```

9\. After you connect to the Spheron instance, then let’s look up all the available keys:

```dockerfile
keys *
```

You will now see an entry for the slug “proof-moonbirds” representing the cache entry for that API call.

<table><tbody><tr><td colspan="1" rowspan="1"><p>1) "proof-moonbirds"</p></td></tr></tbody></table>

## Benefits of Deploying DragonflyDB with Spheron Compute

Deploying your app on Spheron Network has many benefits, including:

1. **Decentralized deployment:** Spheron Network allows developers to deploy their applications to a decentralized network. This means your app is not dependent on a single centralized server, making it more resilient to failures and attacks.
    
2. **Continuous deployment:** Spheron offers continuous deployment for apps, which means your application will be automatically deployed whenever you push changes to your repository. This can significantly speed up the development process and allow for quick rollouts of new features and bug fixes to your app.
    
3. **Simplicity and Speed:** Spheron Compute's user-friendly interface and streamlined deployment process make it easy for both beginners and experienced users to set up DragonflyDB quickly. You can save valuable time that would otherwise be spent on server provisioning and configuration.
    
4. **Spheron Marketplace:** Spheron supports 25+ different instances to deploy, such as Redis, PostgreSQL, MySQL, Grafana, substrate, stride, kyve, etc.
    
5. **Cost-Efficiency:** Spheron Compute provides cost-effective solutions, ensuring you get the most out of your resources. You can choose the plan that aligns with your budget and scale as needed without breaking the bank.
    
6. **Reliability and Performance:** Spheron's infrastructure is designed for stability and high performance. Your DragonflyDB will run smoothly, ensuring you have access to your data when you need it, without interruptions.
    
7. **Flexibility:** With a variety of instance plans and the ability to create custom plans, you can tailor your deployment to meet your specific requirements. This flexibility allows you to optimize your resources for the best performance.
    
8. **Persistent Storage:** Spheron Compute offers the option to add persistent storage, ensuring your data is safe and accessible even if the instance is updated or replaced.
    
9. **Scalability:** Whether you're starting small or planning for growth, Spheron Compute allows you to scale your DragonflyDB deployment with ease. You can handle increasing data volumes and growing user demands effortlessly.
    
10. **Support and documentation:** Spheron provides comprehensive documentation and support, helping you navigate any challenges you may face during deployment and development.
    

## Conclusion

In summary, combining DragonflyDB with Spheron to cache data in a Nest.js API shows much promise for improving web performance. Combining DragonflyDB's speedy caching abilities with Spheron's user-friendly and reliable infrastructure presents a compelling solution for modern development.  Setting it up locally or on Spheron is straightforward and user-friendly. It allows developers to deliver faster, scalable, and resilient services while optimizing resources and managing costs effectively.

Using DragonflyDB with a Nest.js API demonstrates clear benefits, notably in faster API response times and reduced reliance on external services like OpenSea. This setup helps improve scalability and lessens the pressure on external services. It enables developers to optimize API performance, take advantage of caching, and efficiently manage data storage, resulting in better user experiences and application scalability.