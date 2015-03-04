###Manual Mode

Regular RC control, no stabilization. All RC inputs are passed through to the outputs. The only ways in which the RC output may be different from inputs are as follows:

* if a configured failsafe or geofence triggers, and ArduPlane takes control
* if the `VTAIL_OUTPUT` option is enabled, then a software VTAIL mixer is applied on the output
* if the `ELEVON_OUTPUT` option is enabled, then a software Elevon mixer is applied on the output