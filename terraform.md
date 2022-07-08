
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


