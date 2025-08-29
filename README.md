# Nutanix NAI 2.4 NKP Product Catalog

This is for NAI Bootcamps only

Forked from https://github.com/nutanix-cloud-native/nkp-nutanix-product-catalog

# Overview

This catalog repository holds all the Nutanix Products and their respective version HelmRepositories and HelmReleases.

# Receipes

## How to create catalog on your management cluster?

<pre>
flux create secret git github-ssh   \
    --url=ssh://git@github.com/WinsonSou/nai-product-catalog.git \
    --private-key-file=.ssh/id_rsa \
    --namespace <workspace_namespace>

nkp create catalog nutanix-product-apps-catalog \
    --branch main \
    --url ssh://github.com/WinsonSou/nai-product-catalog \
    --secret github-ssh \
    --workspace <workspace_name> 
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

## How to use Mindthegap to create bundle
<pre>
mindthegap create bundle --images-file images.yaml
</pre>

## How to use Mindthegap to push bundle
<pre>
mindthegap push bundle --bundle bundle.tar \
    --to-registry <registry_url> \
    --to-registry-username <registry_username> \
    --to-registry-password <registry_password> \
    [--to-registry-insecure-skip-tls-verify]
</pre>