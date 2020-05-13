# bash-terraform-aliases
collection of aliases to help with Terraform usage

# usage
```
$> AWS_DEFAULT_REGION=us_west_2
$> tfip aws-profile-name
$> tfa aws-profile-name file.plan
```

or

```
$> AWS_DEFAULT_REGION=us_west_2
$> tfip my_profile 
$> tfa my_profile 
```

or

```
$> AWS_DEFAULT_REGION=us_west_2
$> AWS_OKTA_PROFILE=my_profile
$> tfip && tfa
```

or

```
$> AWS_DEFAULT_REGION=us_west_2
$> AWS_OKTA_PROFILE=my_profile
$> tfip 
$> tfa my_proflie /tmp/path/to/file.plan
```

# notes
The `tfip` will `init` and build a plan file which is stashed `/tmp/${profile}_${GIT_BRANCH}_$(date +%s).plan`. Like `/tmp/my_profile_bugfix_git_branch_name_1589390665.plan`.  The plan file path also gets exported out to an environment variable `TERRAFORM_PLAN`.  The `tfa` will check for a value stored in `TERRAFORM_PLAN` if a plan file is not given as the second arg.

Assumes appropriate configurations of `aws-okta` and `~/.aws/conf`.

