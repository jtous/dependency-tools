dependency-tools
================

Set of java classes using `nm` (from binutils) to extract dependencies between object files.

Contains :

mind-violation
--------------

Executable used to identify *hiden* dependencies between Mind components.
A dependency is considered *hiden* if it isn't formally explicited in the .adl file of the component.

Usage :
mind-violation buildFolder


Hidden dependencies are extracted from component definitions (not instances).
Retreiving wich object file belongs to which component definition, is done by reversing the output file naming convention of the compiler.

Three files will be created :

1. HidenDependenies.txt
2. HidenDependencies.dot
3. HidenDependencies.csv

.txt file describe textually, component by component, external symbols used, or external symbols exported.

.dot file are suitable to be ploted using graphviz tools, components are represented by nodes, and hidden dependencies by directed edge. The explicited dependencies (ADL diagram) are not shown on this diagram.

.csv file export dependencies as a Dependency Structur Matrix in csv format.


object-dependencies
-------------------

Executable used to extract dependencies from legacy C compilation.

Can output :
1. A .dot file (which is not usable for real life project)
2. A .csv file suitable to be treated by CAM software (Cambridge Advance Modeling http://www-edc.eng.cam.ac.uk/cam ) for clustering or fragmenting. This representation is especialy usefull to extract implied architecture from legacy code.