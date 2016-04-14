# Pivotal Cloud Foundry Concepts for CS Noobs

# CLI

The PCF CLI is the Command Line Interface. Behind every CLI is an API. While an API simply serves standard requests or returns error codes, a CLI can be an additional layer of support for the end user. Some of the things a CLI can help with include catching error cases if wrong or missing arguments are passed in, offering help by listing endpoints you can invoke, or offering suggested calls you may have intended to make if you made a typo. If you are typing y/n to any questions, you are talking to a CLI. If you are receiving error codes such as a 400, you are talking to the API. Getting to know the cf CLI is well worth your time.

# Orgs Spaces Users Roles

In order to use the CF CLI, you need to login as a user. Every user is given a set of roles, such that the CLI can know if the user has a right to make the calls it is making. Additionally, many commands have to do with managing apps. Apps are organized in, you guessed it, orgs. And orgs are linked to one or more spaces. Some cf CLI commands take in an org name and a space name (such as the —— command, that shows you the users in a given org and space). These commands only execute if the invoker is a user with priveleges to that org and space. This is also useful because if you want Hakeem to manage one app and Thiri to manage another, you can add them both to your org but link each to the relevant space. 

# Manifest

You will see Manifests a lot in your time here. There are BOSH manifests, Ops Manager Manifests (though maybe not anymore!), App Manifests….PIVOTAL LOVES YAML. When you hear manifest, make sure you know which manifest is being talked about. They all generally serve the same purpose. They are YAML files with certain fields defined to preconfigure whatever service they belong to. In the case of an Application Manifest, it requires the field X to do Y. In a BOSH Manifest, it needs jobs to know which network to assign to them.

# Domains and Routes

Domains and routes can get confusing sometimes, so be sure to understand this part thoroughly. A command you will find yourself using a lot is `cf apps` and `cf routes`. This will tell you each app you have, the domain it has (unique), and the route that maps to it (can be shared). Domains are pretty much the name of the app. The end user might never know it. The route is what they type into the browser. They have no idea if there is load balancing or if there are multiple app instances serving that route. ???

# Services

Ah. Everything is a service in a way so it gets confusing here too. Think of a service as any third party software that you can link your app instance to and use. Someone else wrote it (usually) and you just link to it from the marketplace. That’s all you need to care about.

# Service Broker
A component of a service which implements the service broker API.


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
