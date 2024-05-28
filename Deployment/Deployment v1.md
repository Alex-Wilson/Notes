
# Step 0: Organization and Utility
We need to at least present the illusion of being organized (entropy go brrr) these are some of the tools I use and how I use them.

[Trello](https://trello.com): A project management tool with the BEST FREE KANBAN BOARD on the internet. Yea I said it. This is amazing for organizing recurring tasks and visualizing work in progress. KANBAN Boards are just chore charts for work but they are simple and effective, especially amongst disparate or under-communicative teammates. Trust me I am an unemployed PM on the internet. 

[Notion](https://www.notion.so/): Where Trello's KANBAN board leaves off, Notion picks up at no cost at all. While I may track progress of one project in Trello to track or plan complex project information I prefer Notion. I also use Notion calendar to integrate project work into my personal lifestyle.

 [Obsidian](https://obsidian.md/): This is a clean markdown editor reminiscent of visual studio code with the novel idea to connect pages via links, enabling analysis and visualization of the "web of knowledge". Basically a wiki I use to connect my thoughts and also reduce the duplication of information. 

[KeePassXC](https://keepassxc.org/):  Its best practice to generate unique secure passwords for every service and website. This will quickly get out of hand and you will need something to organize the passwords. This is the trendy password manager amongst the other (alleged) humans on the internet seems like everyone trusts this project despite being a very small team. 

[Visual Studio Code](https://code.visualstudio.com/): "FOSS" brought to you by Microsoft. Amazing ecosystem of plug-ins, customizable, and minimal. Considering we are going to use other Microsoft products/services in our stack we should leverage these tools as much as possible to accelerate development. 

[VirtualBox](https://www.virtualbox.org/): "FOSS" brought to you by Oracle. Incredible Type 2 Hypervisor. Drag and drop VM creation from ISO file. I plan to use Debian as the host OS for the web server. I do not use WSL out of respect for Stallman so I will use this to test code before it is pushed to our production servers. There are better ways to do this but I want to avoid service interruptions and reduce VPS costs. 

[Mozilla VPN](https://www.mozilla.org/en-US/products/vpn/): Sometimes you may want to connect from a different network or from a different location. For $5 Mozilla gives you everything you need except access from outside the US.

Git:

# Step 1: Email
[Gmail](https://www.gmail.com)
Setup a new email from a trusted vendor or roll your own. This email should be used across the services that the site requires to function.

# Step 2: Domain Name Selection and Purchase 
[SquareSpace](https://www.squarespace.com/)
It might not seem like it, but there are A LOT of possible combinations of letters and numbers to represent a website's "address"! The best of those addresses seem to be the ones which are short, memorable, and contextual. Domain registration is like putting your name on a mailbox to claim the associated address. When you register a domain name, you’re telling everyone, “This address belongs to me!” so they know where to find your website.

Not all names are available because someone else might already be using it. You can go to websites called "domain registrars" (like [Namecheap](https://www.namecheap.com/), [GoDaddy](https://www.godaddy.com/), or [Bluehost](https://www.bluehost.com/)) to see if your chosen name is available. They have a search box where you type in your name to check.

If your name is available, you can buy it. You will need to make an account. I recommend using the same email as created in step one. You will pay a small amount of money every year to keep the domain. The registrars will guide you through filling out some information (like your name and email) and then you will be prompted to pay. 


# Step 3: Choose a Hosting Provider 
[DigitalOcean](https://www.digitalocean.com/)
While I love seeing "home racks" on the networking subreddit I still encourage users to try to take advantage of the cloud when they are learning to code as it can bear some burden and provide quality of life. Consider the type of website you're building (e.g., blog, e-commerce, portfolio) and its resource needs (e.g., traffic volume, storage, bandwidth). Determine if you need specific technologies (e.g., PHP, MySQL, SSL) or support for particular platforms (e.g., WordPress, Joomla, Magento).

Make an account and log-in. Pay for the server it should be $5 or $10 per month.

# Step 4:  Droplet Creation

Log in and create a digital ocean project if you haven't already. We will need a project to create a droplet. A droplet is basically a docker container, or someone else's computer we are paying to use.

Open PowerShell on your local machine. NOT THE DROPLET. Use the following command to generate a folder and change to that newly created folder. 
```powershell 
mkdir keys\
cd keys\
```

Generate public private key pair for root user using RSA, with a key length of 4096 bits, with a comment of "root@example" at the specified path. Answer all the prompts.
```powershell 
ssh-keygen -t rsa -b 4096 -C "root@example.com" -f  \keys\root_id_rsa 
```

Generate public private key pair for developer user using RSA, with a key length of 4096 bits, with a comment of "root@example" at the specified path. Answer all the prompts
```powershell
ssh-keygen -t rsa -b 4096 -C "USER_NAME@example.com" -f  \keys\USER_NAME_id_rsa 
```

The contents of the \keys\ folder should resemble:
 -developer_id_rsa
 -developer_id_rsa.pub
 -root_id_rsa
 -root_id_rsa.pub

One thing that you can do is use the keyring feature in KeePassXC to add these files and then remove them from the computer. It will also help you track passwords for the keys if one was set.


Navigate back to Digital Ocean in the browser. Create a droplet by naviagating to the droplets tab and clicking the "New Droplet" button. Select the NY datacenter and choose Debian version 12 as the Operating System. Pick the plan with 1GB/CPU, 25GB SSD, 1 TB transfer. It will ask how you want to access the server, remove the selection of password by selecting SSH.  

You will be prompted to paste the contents of the "root_id_rsa.pub" file to Digital Ocean (or copy the key from the keyring in KeePassXC) at the droplet creation screen when asked for SSH keys. This can also be done by adding a public key to Digital Ocean and then adding it as a log-in method via the droplet control panel. 

Ensure that IPv6 is enabled. Enable auto back up once a week. Lastly name the droplet.

Press "Create Droplet" to finish!

# Step 5: Connect to Droplet
Digital Ocean should have an animation and will then show you the list of droplets you own. Click on the droplet that was just created. You should be able to see lots (and lots) of information about the droplet. Take note of the IPv6 address. Copy the IPv6 address.

Open PowerShell on you local machine. Establish an SSH connection with the droplet by running the following command, replacing the capitalized text with the actual server IPv6 adress :
```powershell
ssh -i '\keys\root_id_rsa ' root@SERVER_IPv6_ADDRESS
```

This should result in a prompt for a password to authenticate via the private key, if one was assigned at creation. If everything works you should be greeted by the Debian terminal. You can verify this by looking at the name of the user in the terminal. On you local PC you likely saw PS C:\user_name@computer_name but now it should look like 'root@DROPLET_NAME'.

You are now connected!

Here are some basic things that you should do on your first time in a new linux environment:

### Update and Upgrade Packages
It is always best to be running the most current version of software for security and usability. 
```bash
apt update #Updates the list of packages
apt upgrade #Upgrades all packages currently in the list
```

### Create User(s)
Avoid using root when possible, instead create users. Give users only the privileges that are essential.  
```bash
adduser USER_NAME #creates the user 'user_name'

#Modify the user profile to add the 'sudo' group for 'username'
usermod -aG sudo USER_NAME
```

### Transfer SSH Keys for User(s)
Adds a copy of the local public key to the server for the user that was just created. **Assuming Windows to Debian**. You could also copy and paste via SSH.  This should be the last time we run a root command. 
```Powershell
scp ~\keys\USER_NAME_id_rsa.pub root@SERVER_IPv6_ADDRESS:/home/USER_NAME/.ssh/
```

Then SSH into the droplet as USER_NAME. Run these commands. 
```bash
chown -R USER_NAME:USER_NAME /home/USER_NAME/.ssh
chmod 700 /home/USER_NAME/.ssh
chmod 644 /home/USER_NAME/.ssh/id_rsa.pub
```