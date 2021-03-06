

**Project description:** The EFP Configurator UI is jxBrowser-based interface that is relying on the underlying Engine to provide details about the presentation of the data in the UI. Specifically, the EFP Configuration Tool defines:

The styles of all controls, including but not limited to fonts, colors, size, layout. The tool uses the charting library Canvas.js for displaying various charts, depending on tha values received from the engine.
The EFP Configuration Tool honors the Engine deciding on the:

control type (e.g. numeric, ranged, combo box, chart)
control labels and values
ordering of controls within the given group (inputs are ordered by Engine's list and outputs as well)
The EFP Configuration tool uses string templates (.stg) that accept java objects that carry those attributes and applies them to the generated HTML

## Architecture
The configuration tool in Simplicity Studio comprises the following components:
<ul>
  <li>EFP Python Engine</li>
  <li>EFP Adapter Pack</li>
  <li>EFP Engine</li>
  <li>EFP Configurator UI</li>
</ul>

The EFP Python engine is code managed by the hardware team; the responsibilities of the EFP Python Engine include:

providing the list of valid EFP parts
providing the list of valid power sources for a given EFP part
providing the list of valid power configurations for a given part/source combination
providing the list of inputs to the calculator portion of the engine, each input consisting of
label/name
control type with which it will be represented in the Config Tool
numeric control, free range
numeric control, with min and max values
String control, free form
single-select combo box control with a list of valid values
default/recommended value to show in the Tool
if ranged control, min and max values
If discrete control, a list of valid values to offer where default must be present in the list
providing the list of output calculations given the set of inputs, each output having:
label/name
type (string, numeric, or a chart)
value for a string or numeric
data structure containing arrays with labels, axes labels, and data for charts
generate header file with calculated register values (for use case 1)
generate data to write to the part using EFM32 USB→I2C bridge chip (use case 2)

## EFP Adapter Pack
The EFP Adapter Pack is a bridge between Java layer in studio and python engine running the python scripts.

## EFP Engine
The EFP Engine provides the API for the configuration tool to use. The EFP engine is responsible for invoking the Python calculator via EFP Adapter Pack. The EFP Engine is stateless, meaning that it has no session and needs no memory of the current state of the calculations. It always calculates new state based on the provided inputs.

In addition to bridging to the EFP python calculator for configuration calculations and output generation, the EFP Engine is responsible for:

<ul>
  <li>serialization/deserialization of the EFP Configuration object to a file.</li>
  <li>creation of the new EFP Configuration object</li>
  <li>adding/removing the configuration file to/from a current project</li>
</ul>

## EFP Configurator UI
 The EFP Configurator UI is jxBrowser-based interface that is relying on the underlying Engine to provide details about the presentation of the data in the UI. Specifically, the EFP Configuration Tool defines:

The styles of all controls, including but not limited to fonts, colors, size, layout. The tool uses the charting library Canvas.js for displaying various charts, depending on tha values received from the engine.
The EFP Configuration Tool honors the Engine deciding on the:

control type (e.g. numeric, ranged, combo box, chart)
control labels and values
ordering of controls within the given group (inputs are ordered by Engine's list and outputs as well)
The EFP Configuration tool uses string templates (.stg) that accept java objects that carry those attributes and applies them to the generated HTML


### 1. Client

Silicon Labs Austin Texas
 
### 2.  Duration

May 2019 - Dec 2019

### 3. Technologies used. 
HTML, Canvas Js, String Template, CSS, Java, SWT, OSGi Services, JFace, RCP, Junit, Git ,Windows 10

### 4. Role 

Individual Contributor

### 5. Responsilbilities

Implementing the EFP Configurator UI.
