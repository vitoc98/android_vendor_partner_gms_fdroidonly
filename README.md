This is a fork of https://github.com/lineageos4microg/android_vendor_partner_gms  
It removes microg (GmsCore, GsfProxy, FakeStore) while keeping F-Droid  
It's meant for a device of mine where i'm forced to use GApps, but i still want F-Droid Privileged Extension built-in

To include them in your build, add a repo manifest file to include this repository as `vendor/partner_gms` and set
`WITH_GMS` to `true` when building.
It probably conflicts with the original repo's code, so don't use them together


Example manifest:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<manifest>
    <project path="vendor/partner_gms" name="lineageos4microg/android_vendor_partner_gms" remote="github" revision="master" />
</manifest>
```

This is only meant for my personal use and **no support will be provided, use it at your own risk**  
Credits all go to the original authors and the relative sources

Note: You do not need to set `CUSTOM_PACKAGES` for the packages to be included when building with [lineageos4microg/docker-lineage-cicd](https://github.com/lineageos4microg/docker-lineage-cicd).

The included APKs are:
 * FDroid packages (binaries sourced from [here](https://f-droid.org/packages/org.fdroid.fdroid/) and [here](https://f-droid.org/packages/org.fdroid.fdroid.privileged/))
   * FDroid: a catalogue of FOSS (Free and Open Source Software) applications for the Android platform
   * FDroid Privileged Extension: a FDroid extension to ease the installation/removal of apps
   * additional_repos.xml: a simple package to include the [microG FDroid repository](https://microg.org/fdroid.html) in the ROM (requires FDroid >= 1.5)
 * microG packages (binaries sourced from [here](https://microg.org/download.html))
   * IchnaeaNlpBackend: Network location provider using Mozilla Location Service
   * NominatimGeocoderBackend: Geocoder backend that uses OSM Nominatim service.
