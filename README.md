# Drupal 8 Linked Data
A collection of scripts and modules to enable Linked Data functionality in Drupal 8 installations.

*This code is in early stages of development!*

## Person Custom Content Type
*Within the [person](person/) folder*

A custom content type module for Drupal 8 representing a Person with RDF mapping

### Install and use guide

Requires the following modules:

Core Drupal Modules
- RESTful Web Services
- Serialization
- HTTP Basic Authentication
- RDF

Other Modules
- REST UI from https://www.drupal.org/project/restui
- JSON-LD from https://github.com/Islandora-CLAW/jsonld

Starting with a fresh Drupal 8 install...

1. Install these first then copy the person folder into drupal/modules/ and install the person module

2. Go to the configuration pages and under web services open the REST configuration

3. Enable Content and select edit

4. Set Granularity to resource and check the GET box under methods

5. Check jsonld and json under Accepted request formats

6. Check basic_auth and cookie under Authentication providers

7. Go to the Content menu and Add content

8. Select person and then fill out the details of your person and save

9. This will bring up the newly create node

10. In the address bar `http://localhost:8080/drupal/node/1` add the format URL query string with type JSON-LD: `?_format=jsonld` -> `http://localhost:8080/drupal/node/1?_format=jsonld`

  This will expose the JSON-LD Data.

11. Module is currently mapped to both schema.org/person and xmlns.com/foaf/0.1/person

12. The title field is mapped to FOAF name the rest are mapped to schema.org

13. Mappings can be viewed in the file rdf.mapping.node.person.yml found under person/config/install/

## License
This code is licensed under the GPL v3. See the [LICENSE](LICENSE) deed in this repository for details.

## Contact
Primary Developer:  
**Paul Firth**  
*Industrial Placement Student*  
CSIRO Land & Water  
Dutton Park, QLD, Australia  
<paul.firth@griffithuni.edu.au>  

Product Owner:  
**Nicholas Car**  
*Senior Experimental Scientist*    
CSIRO Land & Water  
Dutton Park, QLD, Australia  
<nicholas.car@csiro.au>
