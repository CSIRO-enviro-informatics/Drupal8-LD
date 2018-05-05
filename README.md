# Person-ContentType-RDFMapped-Drupal
A custom content type module for Drupal 8 representing a Person with RDF mapping

Install and use guide.

Requires the following modules

Core Drupal Modules
- RESTful Web Services
- Serialization
- HTTP Basic Authentication
- RDF

Other Modules
- REST UI from https://www.drupal.org/project/restui
- JSON-LD from https://github.com/Islandora-CLAW/jsonld

Starting with a freash Drupal 8 install.

Install these first then copy the person folder into drupal/modules and install the person module.

Go to the configuration pages and under web services open the REST configuration

Enable Content and select edit.
 
Set Granularity to resource and check the GET box under methods.
Check jsonld and json under Accepted request formats.
Check basic_auth and cookie under Authentication providers.

Go to the Content menu and Add content.
Select person and then fill out the details of your person and save.
This will bring up the newly create node.
in the address bar http://localhost:8080/drupal/node/1 add ?_format=jsonld

http://localhost:8080/drupal/node/1?_format=jsonld

This will expose the JSON-LD Data.

Module is currently mapped to both schema.org/person and xmlns.com/foaf/0.1/person

The title field is mapped to foaf name the rest are mapped to schema.org 

Mappings can be viewed in the file rdf.mapping.node.person.yml found under person/config/install/