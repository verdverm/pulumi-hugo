---
title_tag: Destroy the Stack | Google Cloud
meta_desc: This page provides an overview of how to destroy a Pulumi stack of a Google Cloud (GCP) project.
title: Destroy stack
h1: "Pulumi & Google Cloud: Destroy stack"
weight: 8
menu:
  clouds:
    parent: google-cloud-get-started
    identifier: gcp-destroy-stack

aliases:
- /docs/quickstart/gcp/destroy-stack/
- /docs/get-started/gcp/destroy-stack/
---

Now that you've seen how to deploy changes to our program, let's clean up and tear down the resources that are part of your stack.

To destroy resources, run the following:

```bash
$ pulumi destroy
```

You'll be prompted to make sure you really want to delete these resources. This can take a minute or two; Pulumi waits until all resources are shut down and deleted before it considers the destroy operation complete.

```
Previewing destroy (dev)

View in Browser (Ctrl+O): https://app.pulumi.com/christian-pulumi-corp/quickstart/dev/previews/0f0d731c-6fca-48e7-871d-4a83fb6a814b

     Type                             Name               Plan
 -   pulumi:pulumi:Stack              quickstart-dev     delete
 -   ├─ gcp:storage:BucketIAMBinding  my-bucket-binding  delete
 -   ├─ gcp:storage:BucketObject      index.html         delete
 -   └─ gcp:storage:Bucket            my-bucket          delete

Outputs:
  - bucketEndpoint: "http://storage.googleapis.com/my-bucket-daa12be/index.html-a52debd"
  - bucketName    : "gs://my-bucket-daa12be"

Resources:
    - 4 to delete

Do you want to perform this destroy? yes
Destroying (dev)

     Type                             Name               Status
 -   pulumi:pulumi:Stack              quickstart-dev     deleted
 -   ├─ gcp:storage:BucketIAMBinding  my-bucket-binding  deleted (6s)
 -   ├─ gcp:storage:BucketObject      index.html         deleted (0.78s)
 -   └─ gcp:storage:Bucket            my-bucket          deleted (1s)

Outputs:
  - bucketEndpoint: "http://storage.googleapis.com/my-bucket-daa12be/index.html-a52debd"
  - bucketName    : "gs://my-bucket-daa12be"

Resources:
    - 4 deleted

Duration: 9s
```

> To delete the stack itself, run [`pulumi stack rm`](/docs/cli/commands/pulumi_stack_rm).
Note that this removes the stack entirely from the Pulumi Cloud, along with all of its update history.

Congratulations! You've successfully provisioned some cloud resources using Pulumi. By completing this guide you have successfully:

- Created a Pulumi new project.
- Provisioned a new storage bucket.
- Added an `index.html` file to your bucket.
- Served the `index.html` as a static website.
- Destroyed the resources you've provisioned.

On the next page, we have a collection of examples and tutorials that you can deploy as they are or use them as a foundation for your own applications and infrastructure projects.

{{< get-started-stepper >}}
