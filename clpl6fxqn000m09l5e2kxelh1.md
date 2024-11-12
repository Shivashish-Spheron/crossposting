---
title: "Deploying a PHP Example Server on Spheron Compute: A Step-by-Step Guide"
seoTitle: "Deploy a PHP Example Server on Spheron Compute: A Step-by-Step Guide"
seoDescription: "Learn how to deploy a PHP server on Spheron Compute with this comprehensive step-by-step guide."
datePublished: Thu Nov 30 2023 12:33:35 GMT+0000 (Coordinated Universal Time)
cuid: clpl6fxqn000m09l5e2kxelh1
slug: deploying-a-php-example-server-on-spheron-compute-a-step-by-step-guide
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1701346090858/f2bedd37-c213-4d7d-828d-3e6aaf65341f.png
tags: deployment, web-development, php, blockchain, web3

---

Are you tired of struggling with complex and time-consuming deployments? Look no further than [Spheron Compute](https://docs.spheron.network/compute/cluster/compute/), a powerful cloud platform that simplifies the process of deploying your PHP applications.

This tutorial outlines the deployment of a PHP server, specifically a 'PHP Example' application, on Spheron Compute. We will start by reviewing the PHP application and Docker setup, and then proceed with deploying it on Spheron using a Docker image name.

By following this tutorial, you will have a fully functional PHP server up and running on Spheron Compute in no time.

## **Prerequisites**

* Basic knowledge of **PHP and Docker**.
    
* Docker installed on your local machine.
    
* An account on [Docker Hub](https://hub.docker.com/signup).
    
* An account on [Spheron](https://app.spheron.network/#/login).
    

### **Step 1: Review the PHP Application**

The PHP application consists of a `index.php` file and a `styles.css` file. The index.php file displays data fetched from an API, and styles.css provides the styling.

**Index.php:**

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Spheron PHP example</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="header">
        <h1>Spheron Network</h1>
        <p class="tagline">Build and deploy applications faster with total control and peace of mind</p>
    </div>

    <div class="container">
        <?php
        // URL of the API
        $apiUrl = "https://jsonplaceholder.typicode.com/posts";

        // Using file_get_contents to fetch data from the API
        $jsonData = file_get_contents($apiUrl);

        // Decoding the JSON data to PHP array
        $posts = json_decode($jsonData, true);

        // Check if the data is correctly fetched
        if (is_array($posts)) {
            // Iterate through each post and display
            foreach ($posts as $post) {
                echo "<div class='post'>";
                echo "<h2>" . htmlspecialchars($post['title']) . "</h2>";
                echo "<p>" . htmlspecialchars($post['body']) . "</p>";
                echo "</div>";
            }
        } else {
            echo "<p>Failed to fetch data from the API.</p>";
        }
        ?>
    </div>
</body>
</html>
```

**Styles.css:**

```php
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background: #f4f4f4;
}
.header {
    background-color: #4CAF50;
    color: white;
    text-align: center;
    padding: 1em 0;
    margin-bottom: 2em;
}
.container {
    width: 80%;
    margin: 0 auto;
}
.post {
    background: white;
    padding: 20px;
    margin-bottom: 20px;
    border-radius: 5px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
h2 {
    margin-top: 0;
}
.tagline {
    font-style: italic;
    color: #ccc;
}
```

  
The PHP code we've created is part of a simple web application that fetches and displays posts from an external API. Specifically, it makes a request to the `JSONPlaceholder API` to retrieve a list of posts. Each post's title and body are then displayed on a web page.

The HTML structure of the page includes a header and a container for the posts, while the linked CSS file (styles.css) applies styling to these elements, such as setting the background color, text alignment, and margins. This setup creates a simple, styled web page where users can view a list of posts fetched dynamically from the API.

### **Step 2: Docker Setup**

**Dockerfile -** The Dockerfile prepares a PHP environment with Apache and copies the application files into the container.

```php
# Use an official PHP image with Apache
FROM php:8.0-apache

# Set the working directory in the container
WORKDIR /var/www/html

# Copy the PHP files and CSS files into the container
COPY index.php styles.css /var/www/html/

# Expose port 80
EXPOSE 80

# Start Apache in the foreground
CMD ["apache2-foreground"]
```

Now create a `.dockerignore` File

It's an optional step but is recommended as a good practice.

```php
.git
.gitignore
Dockerfile
.dockerignore
README.md
*.md
```

### **Step 3: Building and Pushing the Docker Image**

**Build the Docker Image:**

````php
``bash
docker build -t giri8spheron/my-php-app:latest .
```
````

**Push to Docker Hub:**

````php
```bash
docker login
docker push giri8spheron/my-php-app:latest
```
````

### **Step 4: Deploying on Spheron Compute**

**Deployment Process**

1. Login to Spheron: Access your Spheron account and navigate to the `compute section.`
    
2. Create a Compute Instance: Select `'on demand'` and create a new cluster.
    
3. Import from Docker Registry: Choose 'Import from Docker registry' and use the Docker image name. In this case its`giri8spheron/my-php-app:latest`.
    
4. **Port Mapping:** Set both the internal and external ports to `80`.
    
5. **Deploy:** Click on 'deploy', keeping other settings at their defaults.
    
6. Wait for Deployment: The process will be completed in a few moments, deploying your `'PHP Example'` server.
    

### Step 5: Accessing Your PHP Server

After deployment, access your PHP server via the provided URL. It will display the content from your `index.php`, styled by `styles.css`.

## Conclusion

Deploying your PHP application on [Spheron](https://spheron.network/) Compute is a streamlined process, demonstrating the efficiency of using Docker and cloud platforms for web application deployment.

## Additional Resources

* [Spheron Compute Documentation](https://docs.spheron.network/marketplace-guide/)
    
* [Docker Official Documentation](https://docs.docker.com/)
    
* [PHP User Manual](https://www.php.net/manual/en/index.php)