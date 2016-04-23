# Pivotal Cloud Foundry Concepts for CS Noobs

### CLI

The PCF CLI is the Command Line Interface. Behind every CLI is an API. While an API simply serves standard requests or returns error codes, a CLI can be an additional layer of support for the end user. Some of the things a CLI can help with include catching error cases if wrong or missing arguments are passed in, offering help by listing endpoints you can invoke, or offering suggested calls you may have intended to make if you made a typo. If you are typing y/n to any questions, you are talking to a CLI. If you are receiving error codes such as a 400, you are talking to the API. Getting to know the cf CLI is well worth your time.

### Orgs Spaces Users Roles

In order to use the CF CLI, you need to login as a user. Every user is given a set of roles, such that the CLI can know if the user has a right to make the calls it is making. Additionally, many commands have to do with managing apps. Apps are organized in, you guessed it, orgs. And orgs are linked to one or more spaces. Some cf CLI commands take in an org name and a space name (such as the —— command, that shows you the users in a given org and space). These commands only execute if the invoker is a user with priveleges to that org and space. This is also useful because if you want Hakeem to manage one app and Thiri to manage another, you can add them both to your org but link each to the relevant space. 

### Manifest

You will see Manifests a lot in your time here. There are BOSH manifests, Ops Manager Manifests (though maybe not anymore!), App Manifests….PIVOTAL LOVES YAML. When you hear manifest, make sure you know which manifest is being talked about. They all generally serve the same purpose. They are YAML files with certain fields defined to preconfigure whatever service they belong to. In the case of an Application Manifest, it requires the field X to do Y. In a BOSH Manifest, it needs jobs to know which network to assign to them.

### Domains and Routes

Domains and routes can get confusing sometimes, so be sure to understand this part thoroughly. A command you will find yourself using a lot is `cf apps` and `cf routes`. This will tell you each app you have, the domain it has (unique), and the route that maps to it (can be shared). Domains are pretty much the name of the app. The end user might never know it. The route is what they type into the browser. They have no idea if there is load balancing or if there are multiple app instances serving that route. ???

### Services

Ah. Everything is a service in a way so it gets confusing here too. Think of a service as any third party software that you can link your app instance to and use. Someone else wrote it (usually) and you just link to it from the marketplace. That’s all you need to care about.

### Service Broker
A component of a service which implements the service broker API.

### Operators
Used to denote the person who configures software and monitors it, may or may not be the end user of the product.
### Client
The end user of the product. Generally the person who just wants to use software to achieve a goal, without being concerned about how to set it up or how it works.
### High Availability
A system or component that is continuously operational for a desirably long length of time. Availability can be measured in percentages, such as "100% operational" or "never failing."
### Installation
Refers to an an instance of a software that you have installed in a location.
### Application Auto-scaling
A service of Pivotal Cloud Foundry, where you as an operator can specify thresholds, minimums, and maximums. In response to load changes on your app, the service scales your app up and down according to the limits you provided. For example you can say, minimum: 3 instances, maximum: 7 instances, low threshold: 15%, high threshold: 60%

![alt text](https://docs.pivotal.io/pivotalcf/customizing/images/configure/3-view-changes.png "Application Auto-scaling Configuration")

See [Application Auto-scaling Configuration](https://docs.pivotal.io/pivotalcf/customizing/autoscale-configuration.html) for more info
### Platform as a Service
Pivotal Cloud Foundry is a PaaS. It provides a platform allowing customers to develop, run, and manage applications without the complexity of building and maintaining the infrastructure. In this case, you bring your own IaaS, we handle the rest. 
[Wikipedia on Paas](https://en.wikipedia.org/wiki/Platform_as_a_service)
### Logging
Logging can mean a few different things in the context of Cloud Foundry. Most generally, you are really hearing about [Loggregator] (https://docs.cloudfoundry.org/loggregator/architecture.html), which is the system for aggregating and streaming logs and metrics from all of the user apps and system components in a Cloud Foundry deployment.
### Provision
A common term in software, generally meaning the automation of steps required to manage user or system access to electronically published services. Basically programmatically setting up software.
### Application Performance Monitoring
Data visualization, metrics, graphs, charts. This also used to be the name of a team that did these very things.
### Application Security Groups
Application security groups (ASGs) act as virtual firewalls to control outbound traffic from the applications in your deployment. See [Application security groups](https://docs.cloudfoundry.org/adminguide/app-sec-groups.html).
### Infrastructure
A very loose term referring to hardware. Usually when someone has infrastructure, they have a bunch of servers (computing power) and disks (storage). Beyond that, there's lots of automation of things and building on top of that.
### Cloud-native
This is a bit of a tricky one. The gist of it is that 'cloud-native' software implies a mentality around building software. One that recognizes that you need a a broad set of components that work together, generally open source and not tied down to one company, as that guarantees constant improvement and lastingness. Ultimately we're talking about barebones managing linux clusters and running containers.
### Pivotal SSO Service
Pivotal Single Sign On is a service (product) that you can get and install on your Ops Manager. You then take all your applications running on PCF and bind them to Pivotal SSO so that they can integrate with enterprise identity providers.
### Self-service platform
The term 'self-service' generally implies software that allows people to secure answers to their inquiries and/or needs through an automated interview fashion instead of traditional search approaches. Pivotal Cloud Foundry provides just that with tools like the CF CLI and REST API. With just a `--help` you can learn how to bind a service or scale an app.
### Continuous Integration
CI means that you deploy little changes and deploy them often such that the code of the various developers is integrating into a shared repository several times a day. Each check-in is then verified by an automated build, allowing teams to detect problems early. Pivotal Cloud Foundry also promotes this with the Concourse product, which is a wonderful CI tool.

### Continuous Delivery
Similar to Continuous Integration, but now instead of just deploying your code often, you're also shipping it to customers often. This goal state is generally harder to achieve but has the wonderful advantage of making upgrades much simpler and less likely to fail because they're little pieces at a time.

### Reseller
Generally used to refer to a customer that takes our product and builds on it to sell something of their own. They vary in how much they change it up but tends to imply a stronger alliance between the companies.

### Cloud Independence
Sort of self explanatory but referring to a software that can hook into different iaases and work the same. For instance, BOSH has a cloud independent part (BOSH Core) and an IaaS specific part (BOSH CPI).

### High Capacity
Something having high capacity is similar to having high throughput. A lot of things can happen to it at the same time and it can handle them.

### Uptime
Generally refers to the time a service is up and working. You want to minimize downtime.

### Real-Time Ingest
This would be a property of logging systems for instance. It would refer to the property of listening on a stream and being able to process input in real time.

scale-out storage
Proxy
Cloud Foundry Foundation
developers
Cloud (quote by paul maritz)
Data
Runtime
managed services
user provided services/plans
blue-green deployments
environment variables
VCAP
service instance
Middleware
OS
virtualization
servers
storage
networking
aws
vSphere
Open Stack
Space
User
Role
Staging
12 factor apps
Cloud Computing
open source
agility
IaaS
Partner
Organization
Space
REST API
Deploying an app
Roles
Permissions
Application Instance
Middleware
Cluster
Components
HA Proxy
PCF vs CF
Ops Manager
PWS
BOSH
Pivotal Elastic Runtime
Application
Loggregator
Cloud Controller API
Service Brokers
Buildpacks
Microservices
Services
cf CLI
Apps Manager
browser
containers
Ant, Maven, Gradle
Application Logs
Application Events
Droplets
Cells/DEAs
VMs
Application Manifests
YAML format
basic cf commands
app name
app host
app domain
app instances
app memory
app path
app route
app timeouts
domains
routes
subdomains
load balancer (HA Proxy)
dns
router
## BOSH
### BOSH release
A bosh release is essentially the software you want bosh to run. You write a release for every single job you could possibly want to run. Every release has a ``spec`` file that describes the job you want to run and where to find the code it needs (such as if you want to reference releases) as well as other dependencies. 
It also has a `monit` file that manages the processes that will run as part of this job.
Lastly it has a `Templates` folder that contains .erb files. Rails requires template files to have the extension of the output type, followed by .erb, so that a name like layout.html.erb indicates a HTML template. Generally these are used for the UI rendering of the overall product.

```
Glossary

| Term          | Definition   |
| ------------- | ------------ |
| API           | Application Programming Interface |
| Availability Zone (AZ)	| A functionally independent segment of network infrastructure, often correlated with geographical region, designated to increase availability and fault-tolerance. A cloud operator can select or assign AZs on platforms such as AWS and vSphere. |
| BOSH          | BOSH is an open framework for managing the full development and deployment life cycle of large-scale distributed software applications. |
| CLI           | Command Line Interface |
| DEA           | Droplet Execution Agent. The DEA is the component in <%=vars.product_short%> responsible for staging and hosting applications. |
| Domains       | A domain is a domain name like `<%=vars.app_domain%>`. Domains can also be multi-level and contain sub-domains like the "myapp" in `myapp.<%=vars.app_domain%>`. Domain objects belong to an org and are not directly bound to apps. |
| Droplet       | An archive within <%=vars.product_short%> that contains the application ready to run on a DEA. A droplet is the result of the application staging process. |
| Managed Services | Services provided by third-parties, but integrated into Cloud Foundry via APIs so that Cloud Foundry users can provision reserved resources and credentials on demand. Also called **Custom Services**. |
| Management    | You can manage spaces and orgs with the cf command line interface, the Cloud Controller API, and the Cloud Foundry Eclipse Plugin. |
| Ops Manager or Operations Manager	| Operations Manager is a web application that you use to deploy and manage a Pivotal Cloud Foundry&reg; PaaS. |
| Org | An org is the top-most meta object within the <%=vars.product_short%> infrastructure. Only an account with administrative privileges on a <%=vars.product_short%> instance can manage its orgs. |
| Routes        | A route, based on a domain with an optional host as a prefix, may be associated with one or more applications. For example, `myapp` is the host and `<%=vars.app_domain%>` is the domain when using the route `myapp.<%=vars.app_domain%>`. It is possible to have a route that represents `<%=vars.app_domain%>` without a host. Routes are children of domains and are directly bound to apps. |
| Service       | A "factory" which produces service instances. |
| Service Instance | A reserved resource provisioned by a service. The resource provisioned will differ by service; could be a database or an account on a multi-tenant application. |
| Spaces        | An org can contain multiple spaces. You can map a domain to multiple spaces, but you can map a route to only one space. |
| Staging       | The process in <%=vars.product_short%> by which the raw bits of an application are transformed into a droplet that is ready to execute. |
| UAA           | User Account and Authentication Service, which provides the technological basis for Dashboard Single Sign-On available to Cloud Foundry users when accessing pertinent Managed Services. |
| Warden        | The mechanism for containerization on DEAs that ensures applications running on <%=vars.product_short%> have a fair share of computing resources and cannot access either the system code or other applications running on the DEA. |
```
