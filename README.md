# eg2-double-target-geometry
Double-target geometry ready to execute on GEMC!

## Usage
Whenever an update is done on the pearl files run:
>./target.pl config.dat

Then, to test the geometry you can use any of the gcards available on the folders. To make a quick test that the geometries, materiales, and volumes are well defined use *test_run.gcard*.

### Using test_run.gcard
Inside this file you can specify the configuration of the dt-structure. The following configurations are available:
- lD2       : Only liquid target is present
- eg2-X     : Only solid target is present. X can be C, Cu, Al, Sn, Pb.
- eg2-X-lD2 : Solid and liquid targets are present. X can be C, Cu, Al, Sn, Pb.

The config is specified in the line:
> detector name="target"         factory="TEXT" variation="eg2-Pb-lD2"/

To execute the gcard, just type:
> gemc test_run.gcard

If everything is good you will see the simulation running :)
## Observations
- All the double-target parts are sensitive type FLUX.
- The liquid target has no sensitivity.
- If the piezomotor is included in the dt-structure some *warnings* will appear when you execute GEMC. The warnings looks like this:
>Polyhedron::SetReferences: List *SomeNumber* is not empty
