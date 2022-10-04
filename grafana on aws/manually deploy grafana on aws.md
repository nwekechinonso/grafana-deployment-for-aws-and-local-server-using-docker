<h1>documentation on how to manually install grafana on aws<h1>


<h2>step 1<h2>

> go to your aws account (you can use the console login method) and create an **ec2 instances**

## step 2

> login into your server**instance** using either ssh or putty. *i used mobaXterm ssh connection*

## step 3

> after successful login, install docker using the command  `sudo yum install docker -y`. after docker installation, start docker with the command `sudo docker service start`

## step 4

> start docker with the command `docker run -d --name=grafana -p 3000:3000 grafana/grafana` telling grafana to run on port **3000**

**note**: configure your security group under inbound and outbound rule to allow traffic from protocol "tcp" "port" "3000".

## step 5

> create an **IAM** user and **group** under **IAM services**. keep your access and security key saved and copied

## step 6

> copy the **Public IPv4 DNS** address under instance details and paste on your browser also indicating the port number. eg: *http://ec2-44-204-79-16.compute-1.amazonaws.com:3000*

## step 7

1. login into **grafana** using the default `username` and `password` **admin**. when logged in, navigate to `add a data source`, select **cloudwatch**, under first tab select `access security key`, input your access and security key and also your region leaving other tab in default.
2. click **save and test**, if successful click on dashboard then import `aws ec2 instance`.
3. click on `ec2` to view metrics.

