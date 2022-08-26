# Let's Play with Bazel

_Bazel is an open-source build and test tool similar to Make, Maven, and Gradle. It uses a human-readable, high-level build language. Bazel supports projects in multiple languages and builds outputs for multiple platforms. Bazel supports large codebases across multiple repositories, and large numbers of users._

_Bazel is a tool that automates software builds and tests. Supported build tasks include running compilers and linkers to produce executable programs and libraries, and assembling deployable packages for Android, iOS and other target environments. Bazel is similar to other tools like Make, Ant, Gradle, Buck, Pants and Maven._

## Create an Ubuntu VM on Azure


Don't forget to check that you are connected to the right _subscription_:

```text
az account show
```

If needed you can change the active _subscription_ with the follwoing command:

```text
az account set --subscription [Name or ID of subscription]
```

Let's create a _resource group_ called `pk-rg-bazel-01` within the _West Europe_ region:

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

You can easily retrieve the public IP address of VM with the following command:

```text
az vm show --show-details --resource-group pk-rg-bazel-01 --name pk-vm-bazel-01 | jq '.publicIps'
```

You can then easily connect to the VM using SSH:

```text
ssh radicel@[Public IP adrress]
```

## References

About Bazel. (2022, August 16). _Intro to Bazel_. Available at <https://bazel.build/about/intro>

About Bazel. (2022, August 16). _FAQ_. Available at <https://bazel.build/about/faq>
