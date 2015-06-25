# Akana API HOOK
![Image of Akana] 
(https://www.akana.com/img/formerlyLOGO8.png) 
[Akana.com](http://akana.com)
### About the API
FHIR - is the a next generation standards framework created by HL7.  FHIR combines the best features of HL7's Version 2, Version 3 and CSA product lines while leveraging the latest web standards and applying a tight focus on implementability. 
- Home Page: FHIR - [Fast Healthcare Interoperability Resources] (http://hl7.org/fhir)
- API Documentation: [FHIR RESTful API] (http://www.hl7.org/implement/standards/fhir/http.html)
- Reference Implementation - HAPI - [FHIR server] (http://fhirtest.uhn.ca)

### Pre-Reqs
- None

### Getting Started Instructions
#### Download and Import
##### Two Options
###### Option 1
- Simply download the FHIR.raml from the src directory
- Create a physical and virtual service using this RAML document

###### Option 2
- Download FHIRAPIHook.zip 
- Login to PolicyManager  example: http://localhost:9900
- Select the parent organization you want to import the API Hook into.  The import will create a whole new organization.  Click on the "Import Package" from the Actions navigation window on the right side of the screen
  - click on button to browse for the FHIR-HL7.zip archive file and click Okay.

#### Verify Import
Only if you chose Option 2 above.
- Expand the organization you imported into.  You should now see a new organization called FHIR-HL7.
- Expand the services folder of the FHIR-HL7.  You should see one physical and one virtual service.

#### Configure Security
- No security is required to access the reference server implementation.  
- If connecting to your FHIR server implementation you will need to apply security.

#### Policy Activation
- No policy activation at this time


#### Offer an Anonymous Contract
- If you performed install option 1:
	- Click on the Virtual Service
	- From the Details tab, click on Offer Contract from the Actions pane on the right
	- Give a Contract Name
	- In the Access Control box, select "Allow consumer (application or organization) users that do not have a contract explicitly assigned"
	- Once contract is created, it will appear in the Consumers section on the Details tab with the Approval Status shown as "Draft".   We need to activate it. 
	- Click on the contract you created.
	- In the Contract Workflow pane over on the right, click on "Activate Contract"
	- You are now done
- If you performed install option 2:
	- On the FHIR_vs0 details page scroll down to Consumers.
	- Click on the Anonymous contract.
	- In the right hand column click the Activate link
	- You are now done

#### Verify Connectivity
- Using your browser http://{Your HOST example: localhost:9901}/fhir/v1/patient
- You should see this response:

```
{
    "resourceType":"Bundle",
    "id":"533fdc25-c4b2-4145-bc95-500595a94253",
    "meta":{
        "lastUpdated":"2015-06-25T17:12:30.665-04:00"
    },
    "type":"searchset",
    "base":"http://fhirtest.uhn.ca/baseDstu2",
    "total":6154,
    "link":[
        {
            "relation":"self",
            "url":"http://fhirtest.uhn.ca/baseDstu2/Patient"
        },
        {
            "relation":"next",
            "url":"http://fhirtest.uhn.ca/baseDstu2?_getpages=a32b3cae-3695-41c8-ae6d-64655678f522&_getpagesoffset=10&_count=10&_format=json&_pretty=true"
        }
    ],
    "entry":[
        {
            "resource":{
                "resourceType":"Patient",
                "id":"35207",
                "meta":{
                    "versionId":"5",
                    "lastUpdated":"2015-06-20T15:32:17.578-04:00"
                },
                "language":[
                    "HV71PjsEKeK5-2I5GrY5"
                ],
                "text":{
                    "status":"generated",
                    "div":"<div><div class=\"hapiHeaderText\"> Aizhan <b>PEREZ </b></div><table class=\"hapiPropertyTable\"><tbody><tr><td>Identifier</td><td>DNI20425239</td></tr><tr><td>Date of birth</td><td><span>19 June 2015</span></td></tr></tbody></table></div>"
                },
                "identifier":[
                    {
                        "system":"www.renaper.gov.ar/dni",
                        "value":"DNI20425239"
                    },
                    {
                        "system":"www.cdrossi.com/pacientes",
                        "value":"291891"
                    }
                ],
                "name":[
                    {
                        "family":[
                            "PEREZ"
                        ],
                        "given":[
                            "Aizhan"
                        ]
                    }
                ],
                "gender":"male",
                "birthDate":"2015-06-19",
                "active":true
            },
            "search":{
                "mode":"match"
            }
        },
        {
            "resource":{
                "resourceType":"Patient",
                "id":"35215",
                "meta":{
                    "versionId":"2",
                    "lastUpdated":"2015-06-19T02:10:42.322-04:00"
                },
                "text":{
                    "status":"generated",
                    "div":"<div><div class=\"hapiHeaderText\"> DINARA <b>PEREZ </b></div><table class=\"hapiPropertyTable\"><tbody><tr><td>Identifier</td><td>DNI20425239</td></tr><tr><td>Date of birth</td><td><span>20 March 1938</span></td></tr></tbody></table></div>"
                },
                "identifier":[
                    {
                        "system":"www.renaper.gov.ar/dni",
                        "value":"DNI20425239"
                    },
                    {
                        "system":"www.cdrossi.com/pacientes",
                        "value":"291891"
                    }
                ],
                "name":[
                    {
                        "family":[
                            "PEREZ"
                        ],
                        "given":[
                            "DINARA"
                        ]
                    }
                ],
                "gender":"male",
                "birthDate":"1938-03-20"
            },
            "search":{
                "mode":"match"
            }
        },
        {
            "resource":{
                "resourceType":"Patient",
                "id":"35231",
                "meta":{
                    "versionId":"1",
                    "lastUpdated":"2015-06-14T10:57:56.555-04:00"
                },
                "text":{
                    "status":"generated",
                    "div":"<div><div class=\"hapiHeaderText\"> GONZALO <b>PEREZ </b></div><table class=\"hapiPropertyTable\"><tbody><tr><td>Identifier</td><td>DNI20425239</td></tr><tr><td>Date of birth</td><td><span>20 March 1964</span></td></tr></tbody></table></div>"
                },
                "identifier":[
                    {
                        "system":"www.renaper.gov.ar/dni",
                        "value":"DNI20425239"
                    },
                    {
                        "system":"www.cdrossi.com/pacientes",
                        "value":"291891"
                    }
                ],
                "name":[
                    {
                        "family":[
                            "PEREZ"
                        ],
                        "given":[
                            "GONZALO"
                        ]
                    }
                ],
                "gender":"male",
                "birthDate":"1964-03-20"
            },
            "search":{
                "mode":"match"
            }
        },
        {
            "resource":{
                "resourceType":"Patient",
                "id":"35239",
                "meta":{
                    "versionId":"1",
                    "lastUpdated":"2015-06-14T11:05:07.933-04:00"
                },
                "text":{
                    "status":"generated",
                    "div":"<div><div class=\"hapiHeaderText\"> GONZALO <b>PEREZ </b></div><table class=\"hapiPropertyTable\"><tbody><tr><td>Identifier</td><td>DNI20425239</td></tr><tr><td>Date of birth</td><td><span>20 March 1964</span></td></tr></tbody></table></div>"
                },
                "identifier":[
                    {
                        "system":"www.renaper.gov.ar/dni",
                        "value":"DNI20425239"
                    },
                    {
                        "system":"www.cdrossi.com/pacientes",
                        "value":"291891"
                    }
                ],
                "name":[
                    {
                        "family":[
                            "PEREZ"
                        ],
                        "given":[
                            "GONZALO"
                        ]
                    }
                ],
                "gender":"male",
                "birthDate":"1964-03-20"
            },
            "search":{
                "mode":"match"
            }
        },
        {
            "resource":{
                "resourceType":"Patient",
                "id":"37",
                "meta":{
                    "versionId":"30",
                    "lastUpdated":"2015-05-20T05:32:40.260-04:00"
                },
                "text":{
                    "status":"generated",
                    "div":"<div><div class=\"hapiHeaderText\"> Hello <b>LEVIN </b></div><table class=\"hapiPropertyTable\"><tbody><tr><td>Identifier</td><td>12345</td></tr><tr><td>Address</td><td><span>534 Erewhon St </span><br /><span>PleasantVille </span><span>Vic </span></td></tr><tr><td>Date of birth</td><td><span>25 December 1974</span></td></tr></tbody></table></div>"
                },
                "identifier":[
                    {
                        "use":"usual",
                        "type":{
                            "coding":[
                                {
                                    "system":"http://hl7.org/fhir/v2/0203",
                                    "code":"MRN"
                                }
                            ]
                        },
                        "system":"urn:oid:1.2.36.146.595.217.0.1",
                        "value":"12345",
                        "period":{
                            "start":"2001-05-06"
                        },
                        "assigner":{
                            "display":"Acme Healthcare"
                        }
                    }
                ],
                "name":[
                    {
                        "family":[
                            "Levin"
                        ],
                        "given":[
                            "Hello"
                        ]
                    }
                ],
                "telecom":[
                    {
                        "system":"phone",
                        "value":"+22 607 123 4567"
                    }
                ],
                "gender":"male",
                "birthDate":"1974-12-25",
                "address":[
                    {
                        "use":"home",
                        "line":[
                            "534 Erewhon St"
                        ],
                        "city":"PleasantVille",
                        "state":"Vic",
                        "postalCode":"3999"
                    }
                ]
            },
            "search":{
                "mode":"match"
            }
        },
        {
            "resource":{
                "resourceType":"Patient",
                "id":"35247",
                "meta":{
                    "versionId":"1",
                    "lastUpdated":"2015-06-14T11:37:13.642-04:00"
                },
                "text":{
                    "status":"generated",
                    "div":"<div><div class=\"hapiHeaderText\"> JOHN <b>SMITH </b></div><table class=\"hapiPropertyTable\"><tbody><tr><td>Identifier</td><td>IDS20425239</td></tr><tr><td>Date of birth</td><td><span>20 March 1964</span></td></tr></tbody></table></div>"
                },
                "identifier":[
                    {
                        "system":"www.personregistry.gov/ids",
                        "value":"IDS20425239"
                    },
                    {
                        "system":"www.labfake.com/patients",
                        "value":"291891"
                    }
                ],
                "name":[
                    {
                        "family":[
                            "SMITH"
                        ],
                        "given":[
                            "JOHN"
                        ]
                    }
                ],
                "gender":"male",
                "birthDate":"1964-03-20"
            },
            "search":{
                "mode":"match"
            }
        },
        {
            "resource":{
                "resourceType":"Patient",
                "id":"35259",
                "meta":{
                    "versionId":"1",
                    "lastUpdated":"2015-06-14T11:49:32.598-04:00"
                },
                "text":{
                    "status":"generated",
                    "div":"<div><div class=\"hapiHeaderText\"> JOHN <b>SMITH </b></div><table class=\"hapiPropertyTable\"><tbody><tr><td>Identifier</td><td>IDS20425239</td></tr><tr><td>Date of birth</td><td><span>20 March 1964</span></td></tr></tbody></table></div>"
                },
                "identifier":[
                    {
                        "system":"www.personregistry.gov/ids",
                        "value":"IDS20425239"
                    },
                    {
                        "system":"www.labfake.com/patients",
                        "value":"291891"
                    }
                ],
                "name":[
                    {
                        "family":[
                            "SMITH"
                        ],
                        "given":[
                            "JOHN"
                        ]
                    }
                ],
                "gender":"male",
                "birthDate":"1964-03-20"
            },
            "search":{
                "mode":"match"
            }
        },
        {
            "resource":{
                "resourceType":"Patient",
                "id":"35269",
                "meta":{
                    "versionId":"2",
                    "lastUpdated":"2015-06-15T04:55:25.612-04:00"
                },
                "text":{
                    "status":"generated",
                    "div":"<div><div class=\"hapiHeaderText\"> Gordon <b>PIETRZAK </b></div><table class=\"hapiPropertyTable\"><tbody><tr><td>Identifier</td><td>asdagsfad</td></tr></tbody></table></div>"
                },
                "identifier":[
                    {
                        "use":"official",
                        "system":"Hospital Number",
                        "value":"asdagsfad"
                    }
                ],
                "name":[
                    {
                        "use":"official",
                        "family":[
                            "Pietrzak"
                        ],
                        "given":[
                            "Gordon"
                        ]
                    }
                ]
            },
            "search":{
                "mode":"match"
            }
        },
        {
            "resource":{
                "resourceType":"Patient",
                "id":"35268",
                "meta":{
                    "versionId":"2",
                    "lastUpdated":"2015-06-15T04:54:00.180-04:00"
                },
                "text":{
                    "status":"generated",
                    "div":"<div><div class=\"hapiHeaderText\"> Gordon <b>JUAN </b></div><table class=\"hapiPropertyTable\"><tbody><tr><td>Identifier</td><td>asdagsfad</td></tr></tbody></table></div>"
                },
                "identifier":[
                    {
                        "use":"official",
                        "system":"Hospital Number",
                        "value":"asdagsfad"
                    }
                ],
                "name":[
                    {
                        "use":"official",
                        "family":[
                            "Juan"
                        ],
                        "given":[
                            "Gordon"
                        ]
                    }
                ]
            },
            "search":{
                "mode":"match"
            }
        },
        {
            "resource":{
                "resourceType":"Patient",
                "id":"35267",
                "meta":{
                    "versionId":"1",
                    "lastUpdated":"2015-06-15T04:52:41.290-04:00"
                },
                "text":{
                    "status":"generated",
                    "div":"<div><div class=\"hapiHeaderText\"><b>JON </b></div><table class=\"hapiPropertyTable\"><tbody><tr><td>Identifier</td><td>123412341234</td></tr></tbody></table></div>"
                },
                "identifier":[
                    {
                        "use":"official",
                        "system":"Hospital Number",
                        "value":"123412341234"
                    }
                ],
                "name":[
                    {
                        "use":"official",
                        "family":[
                            "Jon"
                        ]
                    }
                ]
            },
            "search":{
                "mode":"match"
            }
        }
    ]
}

```

- If you didn’t receive this response, verify the HAPI server is up and running.  See the HAPI url at the top of this readme.

### Modify and Build
In the event you need to change the API Hook.   Here are the instructions to do so. 

### License
Copyright 2015 Akana, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

