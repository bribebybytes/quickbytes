Complexity in managing containers brings us the need for an Orchestrator. One well-known production grade container Orchestrator is Kubernetes. Soon after using all the YAML manifests to define and refine your clusters, you realize a need for an easy use Graphical User Interface or GUI to easy glance through your cluster. 
Both you operations and developer teams needs an easy way to look through the complex setup that has been put in place. 
The first option everyone see is Kubernetes Dashboard that ships with Kubernetes, soon after setting up and using it we realize its complex to secure and expose to all users in our organization. And you start looking for alternatives. 
Imagine a GUI over kubernetes that can easily shows all your resources in an appealing interface and not only that it also warns you if you are missing some best practices. Sounds interesting? Welcome to Kubevious - the obvious GUI for Kubernetes.
This is NarainKrishh and you are watching..

Before we jump, we already discussed multiple GUIs in our channel
1. K9S - VIM like interface with lots of shortcuts to scroll through your cluster.
2. Kubernetes Lens IDE - A desktop application that can connect to clusters remotely and manage your resources.
3. Octane - Another IDE for kubernetes we used in some of our videos.

What is your favourite IDE or GUI or Dashboard when it comes to Kubernetes, Comment that below and lets discuss about it.

Today we are going to see about Kubevious, this IDE, takes not so obvious approach with features like analysing your cluster for missing best practices and over that you can configure your own organization policies to enforce, sounds cool right. Stay till the end of this video I am going to explain every bit of it in detail.

sudo vi /lib/systemd/system/code-server@.service
sudo systemctl restart code-server@narayanan_kmu.service
sudo systemctl daemon-reload
sudo systemctl restart code-server@narayanan_kmu.service
sudo systemctl status code-server@narayanan_kmu.service


air-frame
gcloud compute ssh --ssh-flag "-L 4100:localhost:4100" quickbytes

code-server 
gcloud compute ssh --ssh-flag "-L 8080:localhost:8080" quickbytes