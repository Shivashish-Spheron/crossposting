---
title: "Maximizing Validator Nodes Efficiency using Docker Containers Powered by Spheron"
seoTitle: "Maximizing Validator Nodes Efficiency using Spheron Docker Containers "
seoDescription: "Optimizing Efficiency, Performance, and Scalability when Running Validator Nodes using Docker Containers Powered by Spheron 
"
datePublished: Tue Mar 12 2024 14:00:22 GMT+0000 (Coordinated Universal Time)
cuid: cltofwadn000308jt7ueb93mf
slug: maximizing-validator-nodes-efficiency-using-docker-containers-powered-by-spheron
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1710246840823/60feebb5-8af5-4b68-a4ec-a47bbc92cc36.png
tags: docker, cloud-computing, blockchain, containers, cryptocurrency, web3, decentralization, spheron, nodes

---

Running a validator node is a great way to contribute to the Web3 ecosystem. When considering running a validator node, you have several options: running your own hardware or using a platform to help you run your server. Running your hardware at enterprise levels of uptime and responsiveness is a very difficult task, requiring redundant power supplies and battery backups, a 24/7 network connection with redundancy, monitoring, alerting, and more.

**For this reason, we will focus on the tradeoffs between running a Validator node on a Docker container vs a Virtual Machine(VM).**

---

## Introduction

When choosing between [Docker](https://www.docker.com/) and [Virtual Machines(VMs)](https://azure.microsoft.com/en-us/resources/cloud-computing-dictionary/what-is-a-virtual-machine), several factors must be considered. 

1. **Resource Utilization:**  Docker containers are more efficient in resource utilization and are more lightweight.  VMs consume more resources since they need to run a full operating system(OS) for each instance. 
    
2. **Deployment speed**:  Docker containers start much faster than VMs because they don't require booting a guest OS.
    
3. **Portability:** Docker containers are more portable because they encapsulate the validator node and its dependencies, allowing you to run them across different environments. VM images and instances are heavier and tightly coupled to the underlying hypervisor and Host OS.
    

Managing Docker containers is generally much easier with tools like Kubernetes. VMs require more management overhead, including provisioning, patching, and maintaining the OS for each instance.

***Spheron makes it super easy to run validator nodes on pre-configured Docker containers, which are the clear choice, as you will see throughout this article.*** *This article will focus on the tradeoffs between running a validator node on a Docker container and using a virtual machine (VM).*  

*We will provide an in-depth comparison of the following factors:*

* *Deployment and Configuration*
    
* *Resource Utilization*
    
* *Performance*
    

---

## What is Spheron Network?

[Spheron Network](https://spheron.network/) is a Web3 infrastructure platform that provides tools and services to decentralize cloud storage and computing. It allows audited data centers to join the Spheron marketplace. Spheron oversees the decentralized and governed nature of the infrastructure, ensuring permissionless access and heightened security for all users. Spheron Compute offers a feature-rich alternative to traditional cloud services at only one-third of the cost.

Spheron offers a [Compute Marketplace](https://docs.spheron.network/marketplace-guide), which allows users to set up valuable tools quickly and easily, whether they want to deploy databases, nodes, tools, or AI. With Spheron, you don't have to worry about the technical stuff, and you can focus on deploying your Node with ease. Spheron Network has partnered with organizations like [Shardeum](https://blog.spheron.network/deploy-and-stake-a-shardeum-validator-on-spheron-in-minutes), [Avail](https://blog.spheron.network/deploy-an-avail-node-in-minutes-using-spheron-compute), [Elixir](https://blog.spheron.network/step-by-step-guide-to-launching-an-elixir-node-with-spheron), [Filecoin](https://filecoin.io/), [Arbitrum](https://arbitrum.io/), etc., to redefine access and promote a more decentralized, inclusive, and community-centric ecosystem.

**Spheron provides features such as Private images, Auto-scale instances, Scale on demand, Real-time instance metrics, Faster GPUs, Free Bandwidths, Terraform Providers and SDKs, Instance health checks, activity, shell access, and more. Spheron provides add-on storage solutions for long-term data storage and edge bandwidth acceleration through its global CDN**[**.**](https://blog.spheron.network/deploy-an-avail-node-in-minutes-using-spheron-compute) **With Spheron**[**,**](https://filecoin.io/) **you can easily set up your nodes in just a few minutes and enjoy low maintenance and operations costs and a great developer experience.**

If you don’t already have a [Spheron account, then sign up here](https://app.spheron.network/#/signup)!

---

## Docker Containers vs Virtual Machines

Docker containers and VM technologies allow you to allocate a portion of a bare metal server to an isolated runtime environment dedicated to a specification application such as a validator node.

Here are some general differences between the two:

| **Feature** | **Docker Containers** | **VMs** |
| --- | --- | --- |
| Kernel | Share host OS kernel, reducing overhead and resource consumption | Run guest OS kernel, which requires more resources and consumes more memory & disk space |
| Overhead | Lower overhead | Higher overhead due to guest OS |
| Isolation | Process-level isolation | Strong isolation b/c of its own OS instance |
| Portability | Portable to any system running Docker daemon | Portable only to specific OS and hypervisor configs |
| Start-up Time | Quicker start-up | Longer cold-start time |

VMs offer stronger isolation, while Docker is more efficient in terms of resource utilization, more portable, and starts up quicker. Docker is the clear choice except for very specific use cases that require direct access to hardware or explicit levels of isolation. In the following sections, we will go through all the reasons that Docker is a superior choice for running validator nodes.

## **Example Deployment:**  Spheron vs VM - Powerloom Snapshotter Lite Node 

In this example deployment, we deploy a Cloud instance, e2-standard-2 VM with 2 vCPU and 8GM of RAM to run a Powerloom Snapshotter Lite Node.  Check out the [Powerloom docs here](https://docs.powerloom.io/docs/build-with-powerloom/snapshotter-node/lite-node/getting-started).

![](https://lh7-us.googleusercontent.com/0BwE3AB1qajsLm2ELQ_8IL9z2cP47VeAyrMIv9OfgWfhLPGh9TRpKJsByROTJzjKd8PXiNsQi8d-_wOeuG45UbB3EZBl5rqqSGvgslQJnaiFyUWFw5Z8rQqwUElwi8TWGh-Xg-Liad7Ixgv8prDt9xc align="center")

On Spheron, we deploy a Ventus Medium instance with 2 CPUs and 4GB of RAM.

![](https://lh7-us.googleusercontent.com/hrislys2jDQUpcslpu90GzheFC9VL9RZg0mMm3AwPQccM_ZjZAeO0f3nancxz2aii08ryW0RrMNeIhO0TxxRIJeckloDfWu4XAgRVFxQcIzGp6bjpYOcbTPTr3Z_D3GUq-b3rfMDn41BwMP-y8MIyXg align="center")

### **Virtual Machine Deployment**

Taking a look at the output of the mpstat command, we can see that:

* Tasks running:  113
    
* **CPU Utilization - User level: 5.17%**
    

![](https://lh7-us.googleusercontent.com/AjowQhAPIL0K6SeN--yWHWSoQ1C3sjNP-NZ2GHpQsUKGfOMI0v2jxUmkTvPBxnNc5U1nSnqy3w7dbiD5hFR_PGYRk2qvdYfX7euOM9s1fWQw6SvqLR_Riu4EzOlSmX3bVf7JkVifXq71z5QX52vLXLI align="center")

We can also see the heavy CPU utilization reflected in the metrics graphs for the cloud VM:

![](https://lh7-us.googleusercontent.com/A0xK7zOIJgcb01TTbjvXBAqkJyv7EzO7BizHfpucy9aRXZDWjZZhc2G5ELRCNFRM2bTqVQZrPYwL7ipTEMoS2brO_lJuifKs8GV5NoqK6Y2bUOYAZ4OqE-TOjqWDGlgYOh1BBvjBfAnyZoHW1bi8yzE align="center")

### **Spheron Dockerized Deployment**

Taking a look at the output of the mpstat command, we can see that:

* **CPU Utilization - User level: 0.09%**
    

![](https://lh7-us.googleusercontent.com/HeFPlwS6QN2FaHH44f8frBtwEWMZoay0YRl1hSGIol4y_dNAWwi_HYWJHYj3H_h-1qm1-qqQXOKj0WUwOmL0c9zCYerJdPZDT9M5DOK-KUSxGX8DTkqutlasTnWRVIMR4I6rVyEPubu-OaJ6yUusn2k align="left")

This snapshot of CPU utilization helps illustrate the much heavier resource load that VM footprints have compared to Docker containers because of all the extra overhead. VM resource utilization can be an order of magnitude or more than Docker containers in many instances, especially with all the extra processes that run in cloud VMs.

**Spheron Docker containers are slim, efficient, and lean!**

## Deployment and Configuration

Managing images for VMs is much more difficult than managing Docker images.  You will need to learn and use automation tools such as Packer or Vagrant to create VM images programmatically using configuration files. You will need to configure the VM itself as well as configure the system to host your application.

VM images are generally heavier and don’t have a universal repository solution like Dockerhub.  VM images need to be updated based on OS patches and updates.  VM Image building and distribution is generally a service that is locked into your specific provider.

By using Docker, you can leverage all the built-in native features of the Docker ecosystem to manage Docker images.

### **Benefits of Using Docker over VMs for Image Lifecycle Management:**

* Native tools for building images, Dockerfiles
    
* No need to configure guest OS
    
* No need to learn separate tools like Packer or Vagrant
    
* More straightforward, less verbose configuration
    
* Lighter weight images
    
* Universal image repository solutions such as DockerHubor Github
    
* Native image building & distribution mechanisms with no cloud platform vendor lock-in
    
* No need to update images based on OS patches or updates
    

Docker is a simpler solution for image lifecycle management with native tools for building images and Dockerfiles, and there is no need to configure a guest OS.  Docker offers a simpler, less verbose configuration for your image-management needs. 

Docker also offers lightweight images, which means faster deployment times and less storage space needed. With universal image repository solutions such as DockerHub or Github, you can easily share your images across teams and environments. 

Docker’s native image building and distribution mechanisms allow seamless integration with no cloud platform vendor lock-in. 

### Deploying a Powerloom Snapshotter Light Node directly to a Cloud VM

VM configuration and provisioning can be quite complicated, with Vagrant files often being dozens of lines.  Here is an example of a Vagrant config file for a Cloud VM:

```javascript
# Usage:
#   $ vagrant up --provider=cloud
#   $ vagrant destroy

# Customize these global variables
$PROJECT_ID = "YOUR_CLOUD_PROJECT_ID"
$JSON_KEY_LOCATION = "/path/to/your/private-key.json"
$LOCAL_USER = "mitchellh"
$LOCAL_SSH_KEY = "~/.ssh/id_rsa"

Vagrant.configure("2") do |config|

  config.vm.box = "cloud/gce"

  config.vm.provider :cloud do |cloud, override|
    cloud.project_id = $PROJECT_ID
    cloud.json_key_location = $JSON_KEY_LOCATION

    # Override provider defaults
    cloud.name = "testing-vagrant"
    cloud.image = "debian-9-stretch-v20180611"
    cloud.machine_type = "n1-standard-1"
    cloud.zone = "us-central1-f"
    cloud.metadata = {'custom' => 'metadata', 'testing' => 'foobarbaz'}
    cloud.tags = ['vagrantbox', 'dev']

    override.ssh.username = $LOCAL_USER
    override.ssh.private_key_path = $LOCAL_SSH_KEY
  end
end
```

You can configure this in the UI, but VM configuration is complicated.  Then, you will need to SSH onto your VM and perform all the configuration manually, typing in commands one at a time.

**Example:**

```javascript
ssh root@your_vps_ip
sudo apt-get update && sudo apt-get upgrade -y
sudo apt-get install git -y
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl 
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

    # Add the repository to Apt sources: 
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
    $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
git clone https://github.com/PowerLoom/snapshotter-lite powerloom-testnet
cd powerloom-testnet
screen -S powerloom
./build.sh
```

### Cloud VM Machine Image

We can see that the Cloud VM machine image is very heavyweight at 10GB

![](https://lh7-us.googleusercontent.com/GccQA0ApP0MkCsAokxsCL8jTij07V7YUzOFHd49O-ZNVlQjONts6UCdNz7r3PUMBfN6Xn00WwIP1MGH1v562EH1y3WSZnRo49MQn0AZXwnVTFpJT54iqPilVkDT9ESywlVTJ9kXk-y4JGd7M_E5G8HQ align="center")

### Deploying a Powerloom Snapshotter Light Node with Spheron

With Spheron, you can use a Dockerfile and leverage automation to do all the hard work. You can also pass the Docker repository in as a parameter or use our Marketplace feature.

```javascript
FROM nikolaik/python-nodejs:python3.10-nodejs18

# Install the PM2 process manager for Node.js
RUN npm install pm2 -g

# Copy the application's dependencies files
COPY poetry.lock pyproject.toml ./

# Install the Python dependencies
RUN poetry install --no-dev --no-root

# Copy the rest of the application's files
COPY . .

# Make the shell scripts executable
RUN chmod +x ./snapshotter_autofill.sh ./init_docker.sh
```

Spheron and Docker make deployment and configuration much more streamlined, more accessible, quicker, and less error-prone.

### Docker Image for use with Spheron

We can see that the **Docker image is 5% the size of the Cloud VM machine image.**

![](https://lh7-us.googleusercontent.com/7l-F7KHLTPmWuznqB8LsMBpCHnkQIwYoSILZpZaXmg_XmaHjDfRsApgKTX_5tztEhnEN1BPDLqwmsrlQej5lPTF97Pj58xUdn0oNIyEU-da-F5o9wAou9Aomjmq6rBgDIPSZnZu0EWuFftTJIhH_iPM align="left")

---

### Resource Utilization

VMs simulate complete hardware environments and require their own dedicated resources, including CPU, memory, and storage space. Each VM needs a separate guest operating system instance, increasing resource overhead. 

Docker containers share the host operating system kernel, reducing resource overhead and allowing for efficient orchestration and management using tools like Kubernetes.

**Benefits of Using Docker over VMs in Terms of Resource Efficiency:**

* No need to simulate complete hardware environments(virtual CPUs, memory & storage, etc).
    
* No need for a guest operating system leads to smaller image size and less resource utilization.
    
* Docker containers share the host operating system kernel greatly reducing resource overhead.
    
* Containers pack into raw metal servers more efficiently, allowing you to squeeze more Docker containers into a server to use all available resources efficiently.
    
* Docker containers can be orchestrated and managed efficiently using tools like Kubernetes.
    

Docker containers are more resource-efficient than VMs because they don't require complete hardware environments to simulate virtual CPUs, memory, and storage. This means you don't need a guest operating system, leading to smaller image sizes and less resource utilization. 

Additionally, Docker containers share the host operating system kernel, greatly reducing resource overhead. They pack into raw metal servers more efficiently, allowing you to squeeze more Docker containers into a server to use all available resources efficiently. Docker containers can also be orchestrated and managed efficiently using tools like Kubernetes.

---

### Performance

Performance is crucial for running validator nodes because the network has strict requirements for uptime and responsiveness. Docker container performance is generally better since they leverage the host OS kernel and run as isolated processes. Containers start quickly and have low overhead.  VMs may have higher performance overhead due to the emulation of hardware and the need to run a separate guest OS. Modern hypervisors and virtualization technologies have improved performance, but a significant gap remains.

### Disk Input/Output

Docker containers share the host OS I/O subsystem, which can cause a bottleneck in certain cases for write-heavy workloads. Validator Nodes, however, are read-heavy workloads, so this is generally not an issue.

### Networking

Docker containers use host networking or bridge networking. With host networking, containers share the host's network namespace, which can provide better performance. With bridge networking, Docker creates a virtual network interface (bridge) and connects containers.

Networking is a big bottleneck for validator nodes since they are very “chatty,” have read-heavy workloads, and must serve a high volume of requests.  Docker helps optimize network performance when running validator nodes.

**Virtual Machine Deployment**

We can see that the GCP VM's Validator node is very chatty and has a high network I/O overhead.

Taking a look at the output of the nethogs command, we can see that:

* **Total Network I/O:  21.209 KB/sec**
    

![](https://lh7-us.googleusercontent.com/7S1AJ8x_abjbEZYPtzlZjEA5IYwBwIoUhFDGQxFWW_-k6ohcxIE4m5GuPuGSIpj_vSTk8JtPcZZNQZgG_o7WWn8eeP_Rw9KddGJ1rXXxXYOGNCrSIqObDE3L1vnLC38XN25iecR_njA3uaMQygR-Gdw align="left")

We can also see this high network throughput in the GCP metrics as well

![](https://lh7-us.googleusercontent.com/IJFsor1vYXO8SiYQggNjeYgWiWCHJSrAywYM58Xd-uh9UizxVKLAWQN5CsbFcIvmhc3KTQ8DDbiB0ZjrFTLrePsngVSFruakoR9O-MOP4s9sJ-PUenuAKChT_ZS0qGegHnvp-umLFGPIhZ28PZDWIoE align="center")

**Spheron Dockerized Deployment**

Taking a look at the output of the nethogs command, we can see that:

* **Total Network I/O:  5.968 KB/sec**
    

![](https://lh7-us.googleusercontent.com/pGBowthzjfdejcnmOGYHFMAtAU_JSIieti7QFtKTYgvAhbgairPvFtx5y-60YZ6WlvWcheWRkw64IES0nxn2PKma416JCgQzq5sSmQkOlJHiM3JRB4O1TUO3xq_UPz494-6b1sXHAkg60qTK7UzeQ2A align="center")

This snapshot of Network utilization helps illustrate the much heavier network I/O load that VMs have vs Docker containers because of all the extra overhead.

### CPU Utilization

Docker Containers are allocated CPU shares to determine their priority for CPU access. This allows them to utilize CPU resources as needed within the constraints set by the Docker daemon. VMs typically have dedicated CPU cores or CPU time slices allocated to them.

Docker containers share the host OS, resulting in lower overhead. VMs run separate OS instances, resulting in higher CPU overhead.

**Virtual Machine Deployment**

Looking at CPU utilization metrics charted over time, we can see the VM is very volatile, bursting up to 30-40% at points.

![](https://lh7-us.googleusercontent.com/KxcYy2PBuzTBK6qYd8wuxlHolmhUfX2EvhQ0OE6Rwgcuas5IlW4WbKFUYgpS51GyjpTvZjuypyn10PqDROVhu09JKtX9_cXhLFFSvcajEI5srhi5jxA7l8nUd8NHAQcmXFsnqZiYmbplRURkK7NMSEU align="center")

**Spheron Dockerized Deployment**

Taking a look at CPU utilization metrics charted over time, we can see the VM is very steady, with utilization between 1% and 6%.

![](https://lh7-us.googleusercontent.com/iFGR9Mm4o5m0LOqNRr3kEAaT3hF9FBcDMCKnHmVpidqwtszyRiXH-6Ql81V9j3rSIwEvFXEu5JBgDk0SfwDDoHj1wo57_VsjMLitkbIibqlrg92BlpPtY0AUX7skg9tKbIHFAW7RutZXDiBAfegR4Ms align="left")

These CPU utilization trend graphs illustrate the heavier resource load that VMs have compared to Docker containers, which can be a very large margin in many cases!

### Horizontal Scaling

Docker containers are lightweight and can be rapidly deployed and scaled up or down with container orchestration tools such as Kubernetes.  They can efficiently utilize CPU resources and new instances can be spun-up or down to meet demand.  VMs have higher startup and deployment overhead which can limit their scalability and elasticity for rapidly changing workloads.

**Benefits of Using Docker over VMs in Terms of Performance:**

* Docker host networking provides better performance
    
* Docker containers have lower network I/O overhead compared to virtual machines because they share the host operating system's network stack.
    
* Docker has reduced context switching and network packet processing overhead.
    
* VMs have higher network I/O overhead due to the additional layers of virtualization.  Each VM has its own network stack, adding overhead for packet processing and routing.
    
* Docker containers use CPU resources more efficiently
    
* Docker containers have lower CPU overhead per instance
    
* Docker containers are easier to scale horizontally and are more elastic
    

Docker containers outperform VMs for several key reasons.  They share the host operating system's network stack, reducing network I/O overhead compared to VMs, which each have their own network stack. Docker has lower context switching and packet processing overhead. Docker containers use CPU resources more efficiently with lower overhead per instance. Finally, Docker containers are easier to scale horizontally and are more elastic. Docker provides improved performance over VMs due to more efficient networking, CPU usage, and scalability.

---

## Benefits of Spheron

Spheron Network web3 decentralized physical infrastructure platform allows you to easily deploy Docker containers to decentralized bare metal servers with a couple of clicks. As we have learned, Docker containers provide a huge number of benefits in terms of running robust, resilient validator nodes effectively.

The Spheron Compute Marketplace enables you to quickly deploy pre-configured validator nodes running on Docker containers to leverage all the benefits of containerization we have learned about in this article.

Spheron validator nodes are cost-effective, elastic, performant, and easy to deploy and manage! Our developer experience-focused platform is flexible and composable, allowing you to deploy Web3 infrastructure using our Web UI, Telegram bots, or even a [DAO](https://blog.spheron.network/managing-compute-and-storage-infrastructure-with-a-dao-based-deployment-pipeline)!

If you don’t already have a [Spheron account, sign up here](https://app.spheron.network/#/signup)!

## Conclusion

Docker offers a simpler, more efficient solution for running validator nodes. From image lifecycle management to native tools for building images and Dockerfiles, Docker is easier to use and more streamlined. Docker doesn’t require a guest operating system, leading to smaller image sizes and less resource utilization. It shares the host OS kernel, reducing resource overhead. 

You can more tightly pack Docker containers into a server to use all available resources more efficiently.  Docker containers can be orchestrated and managed efficiently using tools like Kubernetes.

Docker containers have reduced network I/O overhead compared to VMs, which each have their network stack. Docker has lower context switching and packet processing overhead.  They are easier to scale horizontally and are more elastic. Docker provides improved performance over VMs due to more efficient networking, CPU usage, and scalability.

Docker is the clear choice for running validator nodes, and Spheron is the simplest, most streamlined, flexible, and cost-effective platform for deploying your Docker containers to decentralized bare-metal computing.

If you need to run a validator node, do yourself a favor and check out Spheron Network today to get up and running in a few clicks!