---
title: "How to Install Fizz Node on Windows WSL: A Step-by-Step Guide"
seoTitle: "How to Install Fizz Node on Windows WSL: A Step-by-Step Guide"
seoDescription: "If you’re looking to install Fizz Node on your Windows machine, you’re in the right place! In this guide, we’ll walk you through the process of setting up"
datePublished: Sun Oct 06 2024 09:52:38 GMT+0000 (Coordinated Universal Time)
cuid: cm1xemw1d000i08l88pizciaw
slug: how-to-install-fizz-node-on-windows-wsl-a-step-by-step-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1728208232835/e392dac4-958f-4574-b971-51d467353865.png
tags: linux, windows, blockchain, nvidia, wsl, web3, gpu, decentralization, spheron, fizz-node

---

xIf you’re looking to install [**Fizz Node**](https://www.spheron.network/fizz/) on your Windows machine, you’re in the right place! In this guide, we’ll walk you through the process of setting up Fizz Node using **Windows Subsystem for Linux (WSL)**. Don’t worry if this sounds complicated—we’ll break it down into easy-to-follow steps so you can get everything up and running smoothly.

For a step-by-step guide on getting started, head to our YouTube Tutorial below.

%[https://www.youtube.com/watch?v=XPLvoVSsgwY&t=79s] 

## **What You’ll Need**

Before we dive into the process, here’s what you’ll need to have on hand:

* A **Windows 10** or **Windows 11** computer with administrative privileges.
    
* An active **internet connection** to download the required software.
    
* A basic understanding of the command line (don’t worry, we’ll guide you through it).
    

Now that we have everything set, let’s start with enabling WSL.

---

## **Step 1: Enable Windows Subsystem for Linux (WSL)**

**Windows Subsystem for Linux (WSL)** allows you to run a Linux environment on your Windows machine. Let’s enable it!

**1\. Open PowerShell as Administrator**

To enable WSL, you’ll need to run PowerShell as an administrator. Here’s how:

* Click the **Start** button (the Windows icon at the bottom-left of your screen).
    
* In the search bar, type **PowerShell**.
    
* Right-click on **Windows PowerShell** from the results and select **Run as administrator**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728199761552/eb795a9e-b247-4b7d-befe-50e87349733a.png align="center")

**2\. Enable WSL in PowerShell**

Once PowerShell is open, type the following command and hit **Enter**:

```plaintext
wsl --install
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728199934011/f2f1db61-f7ca-4f11-8ad9-3ee59ed9ba7f.png align="center")

This command will:

* Enable the WSL feature.
    
* Enable the Virtual Machine Platform feature.
    
* Install the latest Linux kernel.
    
* Set **WSL 2** as the default version.
    
* Download and install a Linux distribution (most commonly, Ubuntu).
    

**3\. Restart Your Computer**

After running the command, if prompted, restart your computer to complete the installation of WSL.

---

## **Step 2: Install a Linux Distribution (Skip the step if Ubuntu is already installed with the WSL command)**

If WSL didn’t automatically install a Linux distribution, or you want to install a specific one like **Ubuntu 22.04**, follow these steps.

**1\. Open the Microsoft Store**

* Click the **Start** button and type **Microsoft Store**.
    

* Click on the **Microsoft Store** app to open it.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728200043468/f0ff5be5-7fab-4660-a3ac-3a6ad5518c54.png align="center")

**2\. Search for Ubuntu**

* In the Microsoft Store, click the search bar at the top.
    
* Type **Ubuntu 22.04** and press **Enter**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728200800458/bc373634-d24f-4c23-9a71-08d6ae049d79.png align="center")

**3\. Install Ubuntu**

* Click on **Ubuntu 22.04 LTS** from the search results.
    
* Hit the **Get** button and wait for the installation to complete.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728200885163/5262e4a5-b268-4b9f-b112-124148deb369.png align="center")

After the installation, launch **Ubuntu** from the Start menu to initialize the setup.

---

## **Step 3: Install Docker Desktop for Windows**

Docker allows you to run applications in isolated environments known as **containers**. This is an important part of setting up Fizz Node.

**1\. Download Docker Desktop**

* Open your web browser and go to the [Docker Desktop download page](https://www.docker.com/products/docker-desktop/).
    
* Click **Download for Windows**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728201057734/eecceb57-91cd-4d01-bc2a-6ff091ac58fa.png align="center")

**2\. Install Docker Desktop**

Once downloaded, find the **Docker Desktop Installer.exe** file (usually in your Downloads folder) and double-click it to start the installation.

**3\. Enable WSL 2 Features**

If during the installation, you’ll be asked to choose your preferred engine. Ensure that the **Use WSL 2 instead of Hyper-V** option is checked.

**4\. Follow Installation Steps**

Follow the on-screen instructions, clicking **OK** or **Next** when prompted. Be sure to accept any agreements along the way.

**5\. Restart Your Computer**

If prompted, restart your computer after the installation completes to ensure Docker is properly installed.

---

## **Step 4: Configure Docker for WSL**

Now that Docker is installed, let’s configure it to work seamlessly with WSL.

**1\. Open Docker Desktop**

* Click the **Start** button and type **Docker Desktop**.
    
* Open the Docker Desktop application.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728201199881/bc134e98-1e02-4195-9c11-773ccc7065d9.png align="center")

**2\. Set WSL 2 as the Backend**

* Click the **Settings** icon (gear icon) in the top-right corner.
    
* In the **General** tab, make sure the **Use the WSL 2-based engine** option is checked.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728201305600/14a43c24-25e2-47fe-93f8-a8bd3a329390.png align="center")

**3\. Enable Integration with Ubuntu**

To ensure Docker works with the Ubuntu environment you installed earlier:

* Click on **Resources** in the left-hand menu.
    
* Then, click on **WSL Integration**.
    
* Toggle on the **Ubuntu** option to enable integration.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728201382310/e7374108-9d78-45c5-8c60-ea5c873150a0.png align="center")

**4\. Apply and Restart**

Once the settings are configured, click **Apply & Restart** to save your changes and restart Docker.

---

## Step 5: Registering Your Fizz Node

Once you’ve completed the requirements to run your own fizz node, setting things up only takes a few quick steps.

**1\. Registering and Configuring Your Fizz Node**

* Open Your Browser: Navigate to [fizz.spheron.network](http://fizz.spheron.network).
    
* Sign up or log in through Gmail or Github.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727785466948/895c0b0c-36c7-413d-81a2-c6228775a46d.png?auto=compress,format&format=webp align="left")

* Click on the **“Register New Fizz Node”** Button.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727785682659/66be315c-fbfc-4f77-a904-36255dd5a457.png?auto=compress,format&format=webp align="left")

* In the next window, select **Linux** as your node's OS from the options provided (MacOS or Linux).
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727785940163/5d72f052-949e-418f-9910-f21fd4da1bdd.png?auto=compress,format&format=webp align="left")

* Now, choose which Nvidia GPU specifications you have. Need help finding your system configuration? [Learn more in our docs here.](https://docs.spheron.network/fizz/setup-fizz#linux-users-how-to-check-your-system-configuration)
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727796892037/b37096b0-89bc-4ccb-b8c6-4c254ed79cc1.png?auto=compress,format&format=webp align="left")

**2\. Resource Details**

Provide accurate information about the resources you're willing to lend, including:

* **CPU cores**
    
* **RAM capacity**
    
* **Available storage**
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727799178275/4a2c1803-543f-42ea-9670-6e5b749b14c0.png?auto=compress,format&format=webp align="left")

3\. **Region**

Select the geographical location where your node is situated. This helps users choose nodes based on their proximity requirements

4\. **Payment Tokens**

Choose the cryptocurrencies or tokens you will accept as payment for your services.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727799317394/77cdac74-5476-4893-8e72-118e9596b038.png?auto=compress,format&format=webp align="left")

**5\. Provider Selection**

This is a crucial step. Choose a provider carefully, considering factors such as:

* **Uptime track record:** A provider with high uptime increases your chances of getting deployments.
    
* **Provider tier:** Higher-tier providers may offer better opportunities.
    
* Overall reputation in the network
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727799365860/2ca8b82f-748b-463d-8eae-af85a0b06783.png?auto=compress,format&format=webp align="left")

9\. Click **“Register Your Fizz Node,** “To complete the registration, you'll need some ETH on the Spheron chain for gas fees. If you don't have any, you can get some from our faucet at [**faucet.spheron.network**](http://faucet.spheron.network).

Once you confirm the transaction, your node will be officially registered in the Spheron network, and you can proceed to the next steps\*\*.\*\*

Boom 💥— You’re officially part of the decentralized revolution!

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcJBhA-GS1kjKyVjwQD_bcX9kRSz3tQDmI3aSP8XLkA0PRYzj3MvN7v-2d6FnAHg2Mzpi0Aq910D49n4F1W5lmcWyUIUmWSOUZreqwFWYuPDghMwzBiRcjv5dDDPKotLsM8s-pcopZ9_EYT9G218ZKfPtZq?key=S36EbtQFjoo36YqATckWRQ align="left")

## **Step 6: Run the Fizz Script**

After successfully registering your node, you need to set up and run the Fizz node client on your machine. This client software connects your node to the Spheron network and manages resource allocation. Follow these steps:

* Access the setup page for your registered node. There, You should find a link to download the [`fizzup.sh`](http://fizzup.sh) [scrip](http://fizzup.sh/)t.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727799722587/f8b28be6-923f-4fec-bcdc-12c9d21aef23.png?auto=compress,format&format=webp align="left")

* **Download the** [`fizzup.sh`](http://fizzup.sh) script to your machine. Save it in a location you can easily access via a ubuntu terminal.
    
* Now that Docker and WSL are set up let’s run the Fizz Node installation script.
    

**1\. Open Ubuntu**

* Click the **Start** button and type **Ubuntu**.
    

* Open the Ubuntu terminal.
    

**2\. Navigate to the Fizz Script**

Determine the location of your **fizzup.sh** script. If it’s in your Windows **Documents** folder, it can be accessed from WSL using the path `/mnt/c/Users/YourName/Documents/`.

In the Ubuntu terminal, type the following command, replacing **YourName** with your Windows username:

```plaintext
cd /mnt/c/Users/YourName/Documents/
```

Hit **Enter** to navigate to the directory.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728204254072/a6b015b7-08c7-4bdd-807a-9c808ec7963d.png align="center")

**3\. Make the Script Executable**

Next, we need to make the script executable. Type this command:

```plaintext
chmod +x fizzup.sh
```

Press **Enter**.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728204293970/54095443-c0fc-440c-8c7f-a89386f2ecdf.png align="center")

**4\. Run the Fizz Script**

* Finally, run the Fizz script with the following command:
    

```plaintext
./fizzup.sh
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728206738551/836653f7-3436-4544-8ec5-5db52267afe3.png align="center")

* Enter your Ubuntu username password when asked.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728204475845/298b445a-a8bf-48ec-9ff9-77b36e0778cd.png align="center")

The script should now execute, setting up Fizz Node in your WSL environment.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728207070722/da7cb7ef-9840-4f5c-9cb1-e3291092e601.png align="center")

**5\. Verify your fizz node is running**

* verify if your Fizz node is running, use the following command:
    
    ```javascript
     docker-compose -f ~/.spheron/fizz/docker-compose.yml logs -f
    ```
    
    If this doesn't work, try:
    
    ```javascript
     docker compose -f ~/.spheron/fizz/docker-compose.yml logs -f
    ```
    
    These commands will show you the logs of your Fizz node, allowing you to confirm it's running correctly.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727800138995/5a2cfe3f-226e-46fe-807f-7b41e152780e.png?auto=compress,format&format=webp align="left")

**6\. Check your fizz status on the dashboard**

Once you've verified the node is running, return to the setup page on the Spheron Fizz App.

* On the setup page, you'll see a **"Check Status"** button and a switch to **"Automatically check status."** Click the **"Check Status"** button to manually initiate a status check for your Fizz node.
    
* Alternatively, you can toggle on the **"Automatically check status"** switch to have the system periodically check your node's status without manual intervention.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1727800455801/f91a3d99-ed67-4dfe-91ec-7f1715016559.png?auto=compress,format&format=webp align="left")
    
* The system will now perform checks to validate if your node is active and correctly configured.
    

The validation process may take a few minutes. During this time, the system verifies your node's connectivity, resource availability, and configuration. Once your node is confirmed active, you will be automatically directed to your Fizz dashboard.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1728207150827/d35bbdc5-1f0a-43b4-b396-357366bd86bd.png align="center")

Congratulations! 🎉 You’ve successfully installed **Fizz Node** on your Windows machine using **WSL**. Now, you can run Linux applications in your Windows environment without the need for a separate Linux machine or virtual machine.

If you encounter any problems, feel free to revisit this guide or consult the official documentation for [WSL](https://docs.microsoft.com/en-us/windows/wsl/) or [Docker](https://docs.docker.com/).

# Earnings and Rewards

Fizz Nodes earn rewards based on two factors: resource contribution and uptime.

* **Resource Contribution**: You’ll earn more if your node provides higher-tier resources such as a powerful GPU or more CPU cores.
    
* **Uptime**: Fizz Nodes must maintain at least 50% uptime within an ERA (24 hours) to receive rewards.
    

The final reward calculation is a combination of the resource performance and uptime factor. This system encourages node operators to maintain stable, reliable operations while rewarding those who contribute higher-quality resources to the network.

On top of that, Fizz Node operators also earn direct payments from users who lease their compute resources. Operators keep 90% of the payment, with a small fee going to the network and providers. You can withdraw these earnings at any time from your dashboard.

## Fizz Node Benefits

Beyond providing decentralized compute resources, running a Fizz Node offers several exclusive perks:

* **Monetize your idle compute power** by selling resources in an open market.
    
* Earn **$FN points** that will eventually merge with **$SPHN** tokens.
    
* Join the first **DePIN Super Compute Network**, designed to distribute energy usage and help reduce carbon emissions.
    
* Become eligible for the **Fizzer Special Discord Role**, unlocking special rewards like **$500 monthly quests**—on top of regular rewards from resource contributions.
    
* **Early Access to Updates & Announcements** – Be the first to learn about Spheron Network's upcoming features so you can prepare and take full advantage.
    
* **And More to Come** – As we approach our token launch, there are plenty of additional perks in the pipeline!
    

# Fizz Nodes: The Easiest Way to Join the DePIN & AI Revolution

At the end of the day, Fizz Nodes represent a new model for decentralized compute—one that’s accessible, profitable, and easy to manage. They’re a critical piece in Spheron’s broader decentralized vision that lets anyone with a modest setup participate in a network traditionally reserved for institutional players.

So if you’ve ever wanted to dip your toes into decentralized compute without needing to break the bank on hardware, now’s your chance. Get your node up and running, and start contributing to the future of decentralized compute today!

---

## **Troubleshooting Tips**

Encountering issues during the setup process? Here are some common troubleshooting tips.

* **Docker Commands Not Working:**
    
    * Ensure that **Docker Desktop** is running. Look for the Docker icon in the system tray (bottom-right corner of your screen).
        
    * Make sure that WSL integration is enabled in Docker settings for Ubuntu.
        
* **Permission Denied Error:**
    
    * If you see a “Permission Denied” error, double-check that you made the script executable with the `chmod +x fizzup.sh` command.
        
* **Can't Find the Script:**
    
    * Remember that Windows drives can be accessed through WSL using the `/mnt/` directory. For instance, `C:\\Users\\YourName\\Documents` becomes `/mnt/c/Users/YourName/Documents` in WSL.
        
* **Still Having Problems?**
    
    * Try running the Ubuntu terminal as administrator.
        
    * Ensure that all software, including Docker and WSL, is up to date.