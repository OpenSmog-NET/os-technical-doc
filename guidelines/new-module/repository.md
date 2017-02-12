# Setting up a new module / functional area git repository

## Module Names

|Abbreviation|Namespaces|Description|
|------------|----------|-----------|
|os||OpenSmog, device and acquisition APIs|
|core||Frameworks, security|
|ops||DevOps, templates, automation|

## Repository Setup

Please follow the general rule of having 1 repository per:
- package
- deployable application
- container

**OR**

- business domain

*Sometimes it may make more sense to have multiple applications within a single repository (internal and public web-apis belonging to a single business domain).*
*In such cases please make sure that the apps do belong to a single business domain.*

While working with a repository please **don't**:
- mix .NET with Js (unless using an ASP.NET MVC application)
- mix packages with deployable apps/containers
- mix things that have no dependencies on each other

## Repository naming convention

Please adhere to the following convention:

```[module]-[submodule]-[app-type(s)]```

Where:
- ```[module]``` **(mandatory)** Is the abbreviated name of the module
- ```[submodule]``` **(optional)** Used if there are multiple applications in the scope of a single module
- ```[app-type]``` **(mandatory)** Used to indicate the type of an application:
    - ```[module]-(...)-pkg```: Library Package (NuGet / NPM etc.)
    - ```[module]-(...)-web```: Public facing web-application 
    - ```[module]-(...)-api```: Public facing external API 
    - ```[module]-(...)-int-api```: Internal facing API
    - ```[module]-(...)-svc```: Long running service
    - ```[module]-(...)-job```: Short running (scheduled) task/job/serverless-function

Use ```[module]-poc-[submodule]-[app-type]``` for proof-of-concept repositories that may eventually be renamed or deleted.

**Always use kebab-case**
Ex: ```os-device-api```
