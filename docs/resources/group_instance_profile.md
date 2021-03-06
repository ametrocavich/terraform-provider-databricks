---
subcategory: "Security"
---
# databricks_group_instance_profile Resource

-> **Note** This resource has an evolving API, which may change in future versions of the provider.

This resource allows you to attach instance profiles to groups created by the [group](group.md) resource.

## Example Usage

```hcl
resource "databricks_instance_profile" "instance_profile" {
    instance_profile_arn = "my_instance_profile_arn"
}

resource "databricks_group" "my_group" {
    display_name = "my_group_name"
}

resource "databricks_group_instance_profile" "my_group_instance_profile" {
    group_id = databricks_group.my_group.id
    instance_profile_id = databricks_instance_profile.instance_profile.id
}
```
## Argument Reference

The following arguments are supported:

* `group_id` - (Required) This is the id of the [group](group.md) resource.
* `instance_profile_id` -  (Required) This is the id of the [instance profile](instance_profile.md) resource.

## Attribute Reference

In addition to all arguments above, the following attributes are exported:

*  `id` - The id in the format `<group_id>|<instance_profile_id>`.

## Import

-> **Note** Importing this resource is not currently supported.
