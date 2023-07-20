This repository contains information and code related to an example that demonstrates the specification of Workflow Nets with Data in Maude.

The structure of the repo is as follows:
* /example : contains the example files:
  * [wfd-nettypes.maude](/example/wfd-nettypes.maude) : the definition of data types and operations used for a general WFD-net
  * [wfd-netstruct.maude](/example/wfd-netstruct.maude) : the structure of the WFD-net in our example
  * [wfd.maude](/example/wfd.maude) : contains the rewrite rules that describe the behaviour of the WFD-net
  * [wfd-pred.maude](/example/wfd-pred.maude) : contains the state predicates used for verification 
  * [wfd-check.maude](/example/wfd-check.maude) : contains the formulas describing data-flow erorrs and termination properties
  * [wfd-run.maude](/example/wfd-run.maude) : contains commands to verify the existence of data-flow errors, the existence of dead transitions and termination properties  
  * [lisiting.txt](/listing.txt) : contains a listing of the results obtained by running the commands in wfd-run


In order to run the verification procedure for the example, cd the example directory and load  wfd-run.maude 


