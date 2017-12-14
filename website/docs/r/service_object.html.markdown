---
layout: "panos"
page_title: "PANOS: panos_service_object"
sidebar_current: "docs-panos-resource-service-object"
description: |-
  Manages service objects.
---

# panos_service_object

This resource allows you to add/update/delete service objects.

## Example Usage

```hcl
resource "panos_service_object" "example" {
    name = "my_service"
    vsys = "vsys1"
    protocol = "tcp"
    description = "My service object"
    destination_port = "32123"
    tag = ["internal", "dmz"]
}
```

## Argument Reference

The following arguments are supported:

* `name` - (Required) The service object's name.
* `vsys` - (Optional) The vsys to put the service object into (default:
  `vsys1`).
* `description` - (Optional) The service object's description.
* `protocol` - (Required) The service's protocol.  This should be `tcp` or
  `udp`.
* `source_port` - (Optional) The source port.  This can be a single port
  number, range (1-65535), or comma separated (80,8080,443).
* `destination_port` - (Required) The destination port.  This can be a single
  port number, range (1-65535), or comma separated (80,8080,443).
* `tag` - (Optional) List of administrative tags.