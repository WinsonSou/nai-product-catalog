# Nutanix NAI 2.4 NKP Product Catalog

This is for NAI Bootcamps only

Forked from https://github.com/nutanix-cloud-native/nkp-nutanix-product-catalog

# Overview

This catalog repository holds all the Nutanix Products and their respective version HelmRepositories and HelmReleases.

# Receipes

## How to create catalog on your management cluster?
<pre>
nkp create catalog nutanix-product-apps-catalog \
    --workspace <workspace_name> \
    --branch main \
    --url https://github.com/WinsonSou/nai-product-catalog
</pre>

## How to list all the catalogs on management cluster?
<pre>
kubectl get gitrepository -n <workspace_namespace>
</pre>
you can get workspace_namespace by running following command
<pre>
nkp get workspaces
</pre>

## How to list all the apps provided by added catalogs on management cluster?
<pre>
kubectl get apps -n <workspace_namespace>
</pre>

## How to install catalog app?
<pre>
From the UI 
</pre>

## How to delete catalog from your management cluster?
<pre>
kubectl delete gitrepository nutanix-product-apps-catalog -n <workspace_namespace>
</pre>

For more details, you can refer to Nutanix Portal for Nutanix Kubernetes Platform documentation.