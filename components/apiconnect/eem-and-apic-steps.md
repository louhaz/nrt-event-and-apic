# Steps for configuring eem and apic 

## Prepare openshift cluster.
If on ROKS, follow instructions here: https://cloud.ibm.com/docs/openshift?topic=openshift-deploy-odf-vpc&interface=ui to enable ODF and operatorhub.

## Follow instructions to install CP4I components using hypersonic repo.
Add MQ, Event Endpoint Management and API Connect capabilities. 

## Add Event Streams cluster to EEM and add topics.
Find external bootstrap route for the ES cluster and use the scram-user to authenticate. Add some of the topics in the cluster to EEM and publish.

## Add a eem-user in keycloak and verify with kcat
Create a new user in eem and add the role eem-viewer. See 
This user can be used to test the non-admin UI and catalog. Try consuming from the topics shared in EEM using kcat and the example snippets in the EEM UI.

## Configure provider organization and developer portal in APIC
In APIC Cloud Manager (login as integration-admin), setup a valid email server and create a provider organization with a new admin user in the API Manager user repository. 

## Add declarative APIs and API Products.
Follow instructions here to setup a secret which allows the CP4I operator to connect to APIC: https://www.ibm.com/docs/en/cloud-paks/cp-integration/16.1.1?topic=resources-using-api-kubernetes-resource#add-the-api-resource-as-a-draft-to-an-api-manager__title__1
