# node-red-contrib-pdf-hummus

[Node-RED](http://nodered.org) Node to be used to extract text from a pdf file making use of hummusjs.


## Install

Run the following command in the root directory of your Node-RED install:

````
    npm install node-red-contrib-pdf-hummus
````

## Usage
This node splits text out of a PDF document making use of the
npm module hummusjs and the text extraction sample.

This early release is a get it working node-red wrappering of the
text extraction sample code, which does more than is actually is needed
by this node. Hence it has a larger than necessary memory requirement.


### Input
The node needs a filename and a PDF input buffer as input.
The filename being written to can be overridden by setting
`msg.filename`.

The document to be added should be passed in as a data buffer
in `msg.payload`.

### Output
The output is a json object on `msg.payload`.
If the split option is selected then an event is sent for each page.

### Sample flow
````
[{"id":"75540143.de239","type":"pdf-hummus","z":"434de041.4e4f4","name":"","filename":"myfile.txt","split":true,"mode":{"value":"asBuffer"},"x":270.5,"y":65,"wires":[["cd04c7ce.3b70c8","a84e0874.451318"]]},{"id":"38aade4f.ab0c12","type":"fileinject","z":"434de041.4e4f4","name":"","x":103,"y":62,"wires":[["75540143.de239"]]},{"id":"cd04c7ce.3b70c8","type":"debug","z":"434de041.4e4f4","name":"","active":true,"console":"false","complete":"false","x":449.5,"y":65,"wires":[]},{"id":"a84e0874.451318","type":"watson-discovery-v1-document-loader","z":"434de041.4e4f4","name":"","environment_id":"","collection_id":"","default-endpoint":true,"service-endpoint":"https://gateway.watsonplatform.net/discovery/api","x":411,"y":133,"wires":[["2e9ac940.1cd4c6"]]},{"id":"2e9ac940.1cd4c6","type":"debug","z":"434de041.4e4f4","name":"","active":true,"console":"false","complete":"true","x":610.5,"y":131,"wires":[]}]
````

## Contributing
For simple typos and fixes please just raise an issue pointing out our mistakes. If you need to raise a pull request please read our [contribution guidelines](https://github.com/ibm-early-programs/node-red-contrib-pdf-hummus/blob/master/CONTRIBUTING.md) before doing so.

## Copyright and license

Copyright 2017 IBM Corp. under the Apache 2.0 license.
