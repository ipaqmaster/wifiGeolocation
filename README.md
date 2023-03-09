# wifiGeolocation

wifiGeolocation is a script for the automatic discovery and jotting down of nearby access points into a database. It also updates inferior datapoints with better data if later encountered.

Complete with the ability to export or import existing data as CSV for Google "My Maps".

## Usage

1. Connect your GPS module of choice and ensure gpsd is active.

2. Put your network interface of choice into monitor mode (Automatic prep planned soon)

3. At a minimum, call `wifiGeolocation/main --interface wlpXxYy`

### Flags

The script supports a few options to begin with:

* `--interface` An interface to work with. Required for normal operation.

* `--debug` To have the script output more information about its activity (Useful for debugging or just keeping an eye on the process)

* `--nomanagement` If you plan to use this script alongside airodump-ng, bettercap or tcpdump with your own channel management method and only want it to come along for the ride without gettng in the way.

* `--importcsv` To import any csv data you've exported from the database or created using an earlier version

* `--exportcsv` To export your datapoints to a CSV for use elsewhere. Useful for data visualisation platforms such as Elasticsearch (Kibana, Lens) or Google's "My Maps" feature.

* `--google` Optional flag alongside `--exportcsv` to split CSV output to 2000 datapoints per csv file and creates multiple files per 2000 points.

* `--skipgps` Skip GPS requirement. Good for offline testing. (Does not write points to db!)
