
---

<h2 align=center>Docker Installation - Ubuntu</h2>

---

<h3><p>
This guide is designed specifically for an Ubuntu machine that is already setup for virtualization, kvm support, and up-to-date. 

---

> <h2>Preparing for Docker</h2>

---

Before we install docker we need to prepare the Ubuntu host for the docker engine and manager. This includes grabbing certificates and other required packages.

Either execute this command, or download the required packages.

- <code>sudo apt-get install ca-certificates curl gnupg lsb-release</code>

1. **ca-cetifications**: for digital certificate management and encryption between thirdparty. (short answer)
2. **curl**: for downloading anything you can imagine
3. **gnupg**: for handling gpg keys 
4. **lsb-release**: for linux standard base information about the system that docker needs to function


Next make a place for the gpg keys, if you use other gpg keys you can place these anywhere.

These make a directory, then download the key and then register it with gpg

- <code>sudo mkdir -p /etc/apt/keyrings</code>
- <code>curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg </code>

This will register the docker repo with 'apt' so that the engine can be downloaded 

- <code>echo "deb [arch=\$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null</code>

Then update apt

- <code> sudo apt-get update </code>

> <h2>Installing Docker</h2>

Now install the required packages from apt

- <code> sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin </code>

If everything worked well you should be able to run 

- <code>docker run hello-world</code>

Which will cause docker to download and run the "hello-world" container.

At this point if youd prefer a cleaner GUI-interface, install docker desktop from:

