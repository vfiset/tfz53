# Disclaimer

This is a quick and dirty adaptation of [tfz53](https://github.com/carlpett/tfz53) to manage Cloud DNS zones instead of Route 53. Tests were not adapted and are completely broken.

The `legacy-syntax` switch has also been completly ignored untested in this version.

# bind_zone_to_tf_gcp
A conversion utility for creating [Terraform](https://terraform.io) resource definitions for Google Cloud DNS from BIND zonefiles.

## Installation
Download the [latest release](https://github.com/vfiset/bind_zone_to_tf_gcp/releases/latest).

## Usage
`bind_zone_to_tf_gcp -domain <domain-name> [flags] > gcp-domain.tf`

## Flags
| Name       | Description                                        | Default         |
|------------|----------------------------------------------------|-----------------|
| -domain    | Name of domain. Required.                          |                 |
| -zone-file | Path to zone file. Optional.                       | `<domain>.zone` |
| -exclude   | Record types to ignore, comma-separated. Optional. | `SOA,NS`        |
| -skip-zone-creation   | Do not create the zone itself, only records | false        |


## Building
If you want to build from source, you will first need the Go tools. Instructions for installation are available from the [documentation](https://golang.org/doc/install#install).

Once that is done, run

```bash
go get github.com/vfiset/bind_zone_to_tf_gcp
cd $GOPATH/src/github.com/vfiset/bind_zone_to_tf_gcp
go build
```

You should now have a finished binary.

This project uses `dep` to manage external dependencies. See the [Github repo](https://github.com/golang/dep) for more information.
