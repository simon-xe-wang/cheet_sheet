
## terraform settings
###  terraform version

```
terraform {
  required_version = ">= 1.2.0"
}
```

### required providers

```
terraform {
 required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.16"
    }
  }
}
```

### Provider Configuration
used in root module. Child module derives the configuration from root module.

```
provider "google" {
  project = "acme-app"
  region  = "us-central1"
}
```

### Provider Version Constraint in child module
```
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = ">= 2.7.0"
    }
  }
}
```

### pass provider configuration when calling module
```

# Configure 2 aws providers for 2 regions
provider "aws" {
  region = "us-west-1"
}

# An alternate configuration is also defined for a different
# region, using the alias "usw2".
provider "aws" {
  alias  = "usw2"
  region = "us-west-2"
}

# An example child module is instantiated with the alternate configuration,
# so any AWS resources it defines will use the us-west-2 region.
module "example" {
  source    = "./example"
  providers = {
    aws = aws.usw2
  }
}
```



