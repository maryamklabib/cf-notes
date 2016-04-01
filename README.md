# cf-notes

The following are intended for use in the markdown/glossary of PCF


[Command Line Interface](#CLI)

# CLI

The CLI is the Command Line Interface. Behind every CLI is an API. While an API simply serves standard requests or returns error codes, a CLI can be an additional layer of support for the end user. Some of the things a CLI can help with include catching error cases if wrong or missing arguments are passed in, offering help by listing endpoints you can invoke, or offering suggested calls you may have intended to make if you made a typo. If you are typing y/n to any questions, you are talking to a CLI. If you are receiving error codes such as a 400, you are talking to the API. Getting to know the cf CLI is well worth your time.

[Orgs Spaces Users Roles] (#OSUR)

# OSUR
In order to use the CF CLI, you need to login as a user. Every user is given a set of roles, such that the CLI can know if the user has a right to make the calls it is making. Additionally, many commands have to do with managing apps. Apps are organized in, you guessed it, orgs. And orgs are linked to one or more spaces. Some cf CLI commands take in an org name and a space name (such as the —— command, that shows you the users in a given org and space). These commands only execute if the invoker is a user with priveleges to that org and space. This is also useful because if you want Hakeem to manage one app and Thiri to manage another, you can add them both to your org but link each to the relevant space. 

[Manifest] (#Manifest)
# Manifest

You will see Manifests a lot in your time here. There are BOSH manifests, Ops Manager Manifests (though maybe not anymore!), App Manifests….PIVOTAL LOVES YAML. When you hear manifest, make sure you know which manifest is being talked about. They all generally serve the same purpose. They are YAML files with certain fields defined to preconfigure whatever service they belong to. In the case of an Application Manifest, it requires the field X to do Y. In a BOSH Manifest, it needs jobs to know which network to assign to them.

[Domains and Routes] (#DR)
# DR
Domains and routes can get confusing sometimes, so be sure to understand this part thoroughly. A command you will find yourself using a lot is `cf apps` and `cf routes`. This will tell you each app you have, the domain it has (unique), and the route that maps to it (can be shared). Domains are pretty much the name of the app. The end user might never know it. The route is what they type into the browser. They have no idea if there is load balancing or if there are multiple app instances serving that route. ???

[Services] (#Services)
# Services
Ah. Everything is a service in a way so it gets confusing here too. Think of a service as any third party software that you can link your app instance to and use. Someone else wrote it (usually) and you just link to it from the marketplace. That’s all you need to care about.