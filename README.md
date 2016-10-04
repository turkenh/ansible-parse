# ansible-parse
Ansible scripts for end to end setup of a parse server also ready for migration and production

The scripts here follows the steps in [How To Host Parse Server tutorial series][1]   by Brennen Bearnes from DigitalOcean Community.

# Steps

## Step 1 - Create Instance 

Create an Ubuntu 14.04 64 bit droplet on DigitalOcean and copy its ip.

![Step 1 - Create Instance](docs/create_instance.gif?raw=true "")

## Step 2 - Update Domain Record 

Update domain record with that ip for the domain you intend to use. (Make sure you set digitalocean nameservers from your domain providers control panel before)

![Step 2 - Update Domain Record](docs/domain_reg.gif?raw=true "")

## Step 3 - Run Ansible Part 1: Prepare For Migration

Edit group_vars/all file for yourself and update hosts file with the ip of your droplet. Then run "ansible-playbook setup-parse.yml"

![Step 3 - Run Ansible Part 1: Prepare For Migration ](docs/run_ansible_p1.gif?raw=true "")

![mongo conn](docs/endofp1.png?raw=true "Mongodb connection string")

## Step 4 - Start Migration

Copy the mongodb conn string in the previous step and start migration for your app on Parse.com

![Step 4 - Start Migration ](docs/start_migration.gif?raw=true "")

## Step 5 - Run Ansible Part 2: Complete Installation 

Go back to terminal where you started ansible installation and press "enter" to continue.

![Step 5 - Run Ansible Part 2: Complete Installation ](docs/run_ansible_p2.gif?raw=true "")

## Step 6 - Verify Installation & Data 

Go to \<your_domain_name\>:4040 and enter "admin/admin" (unless you changed it with parse_dashboard_user and parse_dashboard_password variables). Once you are ok with the data, go back to parse.com and finalize migration.

![Step 6 - Verify Installation & Data ](docs/verify.gif?raw=true "")

[1]: https://www.digitalocean.com/community/tutorial_series/how-to-host-parse-server
