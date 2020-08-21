# Dataflow Utils

- Requires 0.0.49 version of the plugin
    - sfdx-mohanc-plugins@0.0.49
    - [How to install the plugin](https://mohan-chinnappan-n.github.io/dx/plugins.html#/1)

### Topics
- [List Dataflow in the orgd](#listdf)
- [Start a Dataflow ](#startDf)
- [List Dataflow Jobs](#listdfj)
- [Stop a Dataflow Job](#stopDfJob)



<a name="listdf"></a>
## List Dataflows in the org 

### Usage 
```

$ sfdx mohanc:ea:dataflow:list -h
Lists Dataflows  

USAGE
  $ sfdx mohanc:ea:dataflow:list

OPTIONS
  -u, --targetusername=targetusername             username or alias for the target org; overrides default target org
  --apiversion=apiversion                         override the api version used for api requests made by this command
  --json                                          format output as json
  --loglevel=(trace|debug|info|warn|error|fatal)  logging level for this command invocation

EXAMPLE

              List Dataflows
              sfdx mohanc:ea:dataflow:list  -u <username> 

```
### Demo
```
$ sfdx mohanc:ea:dataflow:list -u mohan.chinnappan.n_ea2@gmail.com
Id,Label
02K3h000000Mu1oEAC,exportOppty2
02K3h000000Mu0vEAC,exportOppty
02K3h000000MtyuEAC,ExportCustomers
02K3h000000MrxWEAS,fruitsdf
02K3h000000Mr7JEAS,The_Motivator
02K3h000000Mr7KEAS,Default Salesforce Dataflow

```

<a name="startDf"></a>
## Start a Dataflow 

### Usage
```
 sfdx mohanc:ea:dataflow:start -h
Starts a given  Dataflow Id  

USAGE
  $ sfdx mohanc:ea:dataflow:start

OPTIONS
  -i, --dataflowid=dataflowid                     Dataflow Id to be run
  -u, --targetusername=targetusername             username or alias for the target org; overrides default target org
  --apiversion=apiversion                         override the api version used for api requests made by this command
  --json                                          format output as json
  --loglevel=(trace|debug|info|warn|error|fatal)  logging level for this command invocation

EXAMPLE

              Start a given dataflow id
              sfdx mohanc:ea:dataflow:start  -u <username> -i <dataflowId>

```
### Demo 
```
$ sfdx mohanc:ea:dataflow:start -i 02K3h000000Mu1oEAC  -u mohan.chinnappan.n_ea2@gmail.com
Dataflow Job Id: 02K3h000000Mu1oEAC
{ progress: 0, status: 'Queued', type: 'dataflowjob' }

```
<a name="listdfj"></a>
## List Dataflow jobs

### Usage
```
$ sfdx mohanc:ea:dataflow:jobs:list  -h
Lists Dataflow Jobs

USAGE
  $ sfdx mohanc:ea:dataflow:jobs:list

OPTIONS
  -u, --targetusername=targetusername             username or alias for the target org; overrides default target org
  --apiversion=apiversion                         override the api version used for api requests made by this command
  --json                                          format output as json
  --loglevel=(trace|debug|info|warn|error|fatal)  logging level for this command invocation

EXAMPLE

              List Dataflow Jobs
              sfdx mohanc:ea:dataflow:jobs:list  -u <username> 

```

### Demo
```
$ sfdx mohanc:ea:dataflow:jobs:list  -u mohan.chinnappan.n_ea2@gmail.com
Id,Label,Status,executedDate
03C3h000002EuDYEA0,exportOppty2,Success,2020-08-21T10:35:55.000Z
03C3h000002EuDJEA0,exportOppty2,Success,2020-08-21T10:35:16.000Z
03C3h000002EuDNEA0,exportOppty2,Success,2020-08-21T10:34:55.000Z
03C3h000002EuCyEAK,exportOppty2,Success,2020-08-21T10:34:03.000Z
03C3h000002Eu8cEAC,exportOppty2,Success,2020-08-21T10:10:40.000Z
03C3h000002Eu8IEAS,exportOppty2,Success,2020-08-21T10:09:10.000Z
03C3h000002Eu88EAC,exportOppty2,Success,2020-08-21T10:08:46.000Z
03C3h000002Eu7zEAC,exportOppty2,Success,2020-08-21T10:07:24.000Z
03C3h000002Eu4uEAC,exportOppty2,Success,2020-08-21T09:59:28.000Z
03C3h000002Eu4pEAC,exportOppty2,Success,2020-08-21T09:58:31.000Z
03C3h000002Ea8REAS,exportOppty2,Success,2020-08-18T18:00:37.000Z
```


<a name="stopDfJob"></a>
## Stop a dataflow job
### Usage

```
$ sfdx mohanc:ea:dataflow:jobs:stop -h
Stops a given  Dataflow Job Id  

USAGE
  $ sfdx mohanc:ea:dataflow:jobs:stop

OPTIONS
  -i, --dataflowjobid=dataflowjobid               Dataflow Job Id to be stopped
  -u, --targetusername=targetusername             username or alias for the target org; overrides default target org
  --apiversion=apiversion                         override the api version used for api requests made by this command
  --json                                          format output as json
  --loglevel=(trace|debug|info|warn|error|fatal)  logging level for this command invocation

EXAMPLE

              Stop a given dataflow job Id
              sfdx mohanc:ea:dataflow:jobs:stop  -u <username> -i <dataflowJobId>
```


### Demo
```
$ sfdx mohanc:ea:dataflow:jobs:stop -i 03C3h000002EuLqEAK -u mohan.chinnappan.n_ea2@gmail.com
Dataflow Job Id: 03C3h000002EuLqEAK
{
  createdDate: '2020-08-21T11:00:02.000Z',
  duration: 17,
  executedDate: '2020-08-21T11:00:07.000Z',
  id: '03C3h000002EuLqEAK',
  jobType: 'user',
  label: 'exportOppty2',
  progress: 1,
  source: {
    id: '02K3h000000Mu1oEAC',
    name: 'exportOppty2',
    url: '/services/data/v49.0/wave/dataflows/02K3h000000Mu1oEAC'
  },
  startDate: '2020-08-21T11:00:02.000Z',
  status: 'Success',
  type: 'dataflowjob',
  url: '/services/data/v49.0/wave/dataflowjobs/03C3h000002EuLqEAK'
}
```


