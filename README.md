# Let's Play with Bazel

_Bazel is an open-source build and test tool similar to Make, Maven, and Gradle. It uses a human-readable, high-level build language. Bazel supports projects in multiple languages and builds outputs for multiple platforms. Bazel supports large codebases across multiple repositories, and large numbers of users._

## Create an Ubuntu VM on Azure

First, let's create a _resource group_ called `pk-rg-bazel-01` within the _West Europe_ region:

```text
az group create --name pk-rg-bazel-01 --location westeurope
```

Then, let's create an Ubuntu _virtual machine_ called `pk-vm-bazel-01` within the `pk-rg-bazel-01` group:

```text
az vm create \
  --resource-group pk-rg-bazel-01 \
  --name pk-vm-bazel-01 \
  --image Canonical:0001-com-ubuntu-minimal-focal:minimal-20_04-lts-gen2:latest \
  --admin-username radicel \
  --generate-ssh-keys \
  --public-ip-sku Standard
```

## References

Aubout Bazel. (2022, August 16). _Intro to Bazel_. Available at <https://bazel.build/about/intro>
