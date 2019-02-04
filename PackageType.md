
### Package Type and Package Structure considerations

#### Package Type 

* 1 Generic type such as `Data`, `Transport`, `Framework`.
    * There are currently 3 different packages that SDK will use (NuGet was only aware of 2 up until few weeks ago). Targeting/Runtime and Apphost packs. This allows for seemless integration of new package types as needed.

* Each package usage (targeting/runtime/apphost) gets its own package type. 
    * This allows for future different experience based on the package type. 

#### Package Structure

The package type introduction won't prevent old clients from installing these packages.

* Using a completely different folder that NuGet does not understand, such as "data". 
    * Whenever installed in older clients, no assets selection will occur, so they'll install but will be inert. 
* In folders that NuGet understands for certain asset groups. 
    * /ref for targeting packages, runtimes/ for the runtime pack. 
    * This allows packaging experiences to seemlessly integrate with these packages.
    * Potential seemless reintegration into NuGet, if ever deemed necesary for NuGet to understand these packages again. 