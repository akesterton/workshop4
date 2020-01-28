# workshop4
Developer Experience Workshops for OCP4.2+

This repo contains all the collateral and material for running the DevEx Workshops for OCP4.2+

To run a workshop request an OpenShift4.2 Workshop via RHPDS.

The workshop has been split into two components, a 'basics' and an 'advanced' module. These are built separately as documents and can be given independently - the course takes about 6-8 hours to do them both depending on attendee level.

Generate the documentations for the attendees using Maven - clone this repo, go to the documentation directories (documentationbasic and documentationadvanced) and run:

mvn clean package -DfacilitatorName='YOUR NAME' -DfacilitatorEmail='YOUR EMAIL' -DfacilitatorTitle='YOUR JOB TITLE' -DwebConsoleUrl='CONSOLE URL FOR OCP4' -DterminalUrl='TERMINAL URL FOR OCP4'

It is worth creating short URLs for the following URLs to be provided to the attendees:

1: The Console URL (the console login point for the attendees)
2: The Terminal URL (the URL for the 'command line in a window' application)
3: The API Endpoint URL (the URL used to make direct calls, primarily for the Tekton chapter)

The terminal URL can be derived by logging on to the RHPDS cluster as the opentlc-mgr user and looking at Networking/Routes for the Terminal application. 

There are a couple of pre-requisites you need to do before starting the advanced course:

Log on as cluster admin (opentlc-mgr)

Go to Operator Hub

Search for ‘Pipeline’

Select the Community OpenShift Pipelines Operator

Install for all namespaces in the cluster

Go to Operator Hub

Select Red Hat Service Mesh

Install for all namespaces in the cluster



