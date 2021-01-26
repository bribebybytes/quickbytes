Complexity in managing containers brings us the need for an Orchestrator. One well-known production grade container Orchestrator is Kubernetes. Soon after playing with all the YAML manifests to define and refine your clusters, you realize a need for an easy use Graphical User Interface or GUI to get a glance through your cluster. 
Both you operations and developer teams needs an easy way to look through the complex setup that has been put in place. 
The first option everyone see is Kubernetes Dashboard that ships with Kubernetes, soon after setting up and using it we realize its complex to secure and expose it to all users in our organization. If you have succeeded using Kubernetes Default Dashboard, comment below, I would like to know how you made that work for you. But most of the you start looking for alternatives.
Imagine a GUI over kubernetes that can easily shows all your resources in an appealing interface and not only that it also warns you if you are missing some best practices. Sounds interesting? Welcome to Kubevious - the obvious GUI for Kubernetes.
This is NarainKrishh and you are watching..

Before we jump, we already discussed multiple GUIs in our channel
1. K9S - VIM like interface with lots of shortcuts to scroll through your cluster.
2. Kubernetes Lens IDE - A desktop application that can connect to clusters remotely and manage your resources.
3. Octane - Another IDE for kubernetes we used in some of our videos.

What is your favourite IDE or GUI or Dashboard when it comes to Kubernetes, Comment that below and lets interact.

Today we are going to see about Kubevious, this IDE, takes not so obvious approach, with features like analysing your kubernetes cluster like
- Text Based Searching
- Hierarchy based configuration access to your full cluster resources
- Impact radius analysis
- Time-Machine - That word itself is so cool.
- Configuration validations
- Capacity planning and list goes on.

 Stay till the end of this video, I am going to explain starting from setup and going to end it with where it can help you in you day to day activities, and dont forget to share with your friends and colleage circle.



###Installation:
The easiest way to install kubevious is using helm and just follow below 3 steps:

```
kubectl create namespace kubevious
helm repo add kubevious https://helm.kubevious.io
helm upgrade --atomic -i kubevious kubevious/kubevious -n kubevious
```

Now that kubevious is running your cluster
Quick way to view is to use kubectl proxy to expose it. You can also create kubernetes ingress if you will like to.

```
kubectl get pods -n kubevious -l "app.kubernetes.io/component=kubevious-ui" -o jsonpath="{.items[0].metadata.name}
kubectl port-forward <<<pod name from above>> 8080:80 -n kubevious  
```

Just for demonstration I am going to deploy argocd, which is kubernetes native CI/CD tool that runs within kubernetes cluster, with lots of related to components, I think it can help us understand kubevious features better. Pls note I could have taken any application that runs in kubernetes for this example.

So let me quickly install argo cd

```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

Now that argocd is installed, lets open our kubervious IDE to check it.

###Search like never before:
Very first amazing feature is this text based feature
