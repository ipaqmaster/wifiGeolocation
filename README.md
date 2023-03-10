# wifiGeolocation

wifiGeolocation is a script for the automatic discovery and jotting down of nearby access points into a database. It also updates inferior datapoints with better data if later encountered.

Complete with the ability to export or import existing data as CSV for Google "My Maps".

## Usage

1. Connect your GPS module of choice and ensure gpsd is active. (The socket usually takes care of this)

2. At a minimum, call `wifiGeolocation/main --interface wlpXxYy`

3. Wait for a GPS lock and the database will start writing.

### Flags

The script supports a few options to begin with:

* `--interface` An interface to work with. Required for normal operation.

* `--loglevel #` Optional verbosity. Verbose=1, Debug=2.
* `--debug`      Quick `--loglevel 2` - To have the script output more information about its activity (Useful for debugging or just keeping an eye on the process)
* `--verbose`    Quick `--loglevel 1`

* `--nomanagement` If you plan to use this script alongside airodump-ng, bettercap or tcpdump with your own channel management method this prevents the script from managing interfaces and channel hopping. Just along for the ride.

* `--importcsv` To import any csv data you've exported from the database or created using an earlier version

* `--exportcsv` To export your datapoints to a CSV for use elsewhere. Useful for data visualisation platforms such as Elasticsearch (Kibana, Lens) or Google's "My Maps" feature.

* `--google` Optional flag alongside `--exportcsv` to split CSV output to 2000 datapoints per csv file and creates multiple files per 2000 points.

* `--skipgps` Skip GPS requirement. Good for offline testing. (Does not write points to db!)
