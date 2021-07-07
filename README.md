# waio-mule4-checksums-demo

This project calculates and validates checksums and provides a demonstration of the Mule 4 Cryptography Module's Calculate and Validate Checksum general operations.  Full write up of demonstration steps are available on 
[here](https://www.whitneyakinola.io/post/calculate-validate-checksum-with-mule-4).

Feel free to use this project to validate any downloaded file.  

## Author
Whitney Akinola [@WhitneyAkinola](https://twitter.com/whitneyakinola)

## Installation
* Clone repo and run the following command in Anypoint Studio 7 or a Mule 4 standalone server. 
```bash
mvn clean package -nsu -DskipMunitTests
```
* Configure local.yaml (properties) file with  original_file_path, tampered_file_path, and  expected_checksum
* Note, sample files are embedded in the src/main/resources folder.  original_file_path, tampered_file_path, and expected_checksum are default values that correspond to sample files. 

## Invoke Flows
This project comes with an original copy and tampered checksum flow.  Use the following 
curl commands to invoke the flows:
```bash
curl get http://localhost:8081/checksum/original 
curl get http://localhost:8081/checksum/tampered
```

## Future Use
Feel free to use this project to build a checksum validation utility with the tampered flow.  However, when validating checksums, you will need to know the original checksum of the document first.  That should be provided by the sender before running the tampered flow.  Make sure to add the original checksum to the expected_checksum property. 

## Further Reading 
* https://docs.mulesoft.com/mule-runtime/4.3/cryptography

## Dependencies
* Mule 4.3.0 EE Runtime
* Mule 4 HTTP Connector
* Mule 4 File Connector 
* Mule 4 Cryptography Module 

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)