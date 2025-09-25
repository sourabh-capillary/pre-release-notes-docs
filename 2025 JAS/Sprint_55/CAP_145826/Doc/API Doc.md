Link to Doc: https://docs.capillarytech.com/reference/update-vendor-metadata#/

Enable or Disable a Vendor

A vendor is an external third-party brand you can use to fulfil your rewards. This API allows you to enable or disable a vendor.

\> 👍 Note  
\>  
\> For detailed information about our APIs and for hands-on testing, refer documentation in \[API overview\](https://docs.capillarytech.com/reference/apioverview) and step-by-step guide on making your first API call in \[Make your first API call\](https://docs.capillarytech.com/reference/make-your-first-api-call).

\# Prerequisites

\* \[ \] Authentication: Basic/OAuth authentication  
\* \[ \] Default access group

\# Resource information

|               |                                                                                       |  
| :------------ | :------------------------------------------------------------------------------------ |  
| URI           | /api\\\_gateway/rewards/core/v1/vendor/\`{vendorId}\`/status/\`{action}\`/brand/\`{brandId}\` |  
| HTTP method   | PUT                                                                                   |  
| Pagination    | NA                                                                                    |  
| Rate limit    | NA                                                                                    |  
| Batch support | NA                                                                                    |

\# API endpoint example

Enabling a vendor: \`https://eu.api.capillarytech.com/api\_gateway/rewards/core/v1/vendor/5/status/enable/brand/3\`

Disabling a vendor: \`https://eu.api.capillarytech.com/api\_gateway/rewards/core/v1/vendor/5/status/disable/brand/3\`

\# Path parameters

\<Table\>  
  \<thead\>  
    \<tr\>  
      \<th\>  
        Parameter  
      \</th\>

      \<th\>  
        Data Type  
      \</th\>

      \<th\>  
        Description  
      \</th\>  
    \</tr\>  
  \</thead\>

  \<tbody\>  
    \<tr\>  
      \<td\>  
        vendorId  
      \</td\>

      \<td\>  
        long  
      \</td\>

      \<td\>  
        Unique identifier of the vendor.  
      \</td\>  
    \</tr\>

    \<tr\>  
      \<td\>  
        brandId  
      \</td\>

      \<td\>  
        Integer  
      \</td\>

      \<td\>  
        Unique identifier of the brand.  
      \</td\>  
    \</tr\>

    \<tr\>  
      \<td\>  
        action  
      \</td\>

      \<td\>  
        Enum  
      \</td\>

      \<td\>  
        Enable or disable the vendor. Supported values:  
        \`enable\`: enable the vendor.  
        \`disable\`: disable the vendor  
      \</td\>  
    \</tr\>  
  \</tbody\>  
\</Table\>

\# Response body

\`\`\`json Enable a vendor  
{  
    "status": {  
        "success": true,  
        "code": 5006,  
        "message": "Vendor status updated successfully"  
    },  
    "vendorRo": {  
        "id": 133,  
        "name": "VENDORHIRE",  
        "brandId": 61,  
        "enabled": true,  
        "isEncryptionRequired": false,  
        "vendorTypes": null,  
        "vendorDetails": null,  
        "type": "REWARDS",  
        "createdBy": 75161973,  
        "lastUpdatedBy": 75161973,  
        "createdOn": 1747307907000,  
        "lastUpdatedOn": 1748350778000,  
        "createdOnDateTime": "2025-05-15T11:18:27Z",  
        "lastUpdatedOnDateTime": "2025-05-27T12:59:38Z",  
        "rank": 1,  
        "code": "Doc0036",  
        "description": "The top priority vendor",  
        "images": null,  
        "videos": null,  
        "encryptionRequired": false  
    }  
}  
\`\`\`  
\`\`\`json Disable a vendor  
{  
    "status": {  
        "success": true,  
        "code": 5006,  
        "message": "Vendor status updated successfully"  
    },  
    "vendorRo": {  
        "id": 133,  
        "name": "VENDORHIRE",  
        "brandId": 61,  
        "enabled": false,  
        "isEncryptionRequired": false,  
        "vendorTypes": null,  
        "vendorDetails": null,  
        "type": "REWARDS",  
        "createdBy": 75161973,  
        "lastUpdatedBy": 75161973,  
        "createdOn": 1747307907000,  
        "lastUpdatedOn": 1748350778000,  
        "createdOnDateTime": "2025-05-15T11:18:27Z",  
        "lastUpdatedOnDateTime": "2025-05-27T12:59:38Z",  
        "rank": 1,  
        "code": "Doc0036",  
        "description": "The top priority vendor",  
        "images": null,  
        "videos": null,  
        "encryptionRequired": false  
    }  
}  
\`\`\`

\# Response parameters

| Parameter                   | Description                                                                                                      |  
| :-------------------------- | :--------------------------------------------------------------------------------------------------------------- |  
| \*\*\`status\`\*\*                | Object containing details about the status of the request.                                                       |  
| \`- success\`                 | Indicates whether the request was successful. \`true\`: Request was successful. \`false\`: Request was unsuccessful. |  
| \`- code\`                    | The status code of the request.                                                                                  |  
| \`- message\`                 | The status message of the request.                                                                               |  
| \*\*\`lastUpdatedOn\`\*\*         | Indicates the timestamp when the vendor redemption was updated. The timestamp is in Epoch time format.           |  
| \*\*\`lastUpdatedBy\`\*\*         | The till ID of the user who last updated the vendor redemption record.                                           |  
| \*\*\`createdBy\`\*\*             | The till ID of the user who created the vendor redemption.                                                       |  
| \*\*\`createdOn\`\*\*             | Indicates the timestamp when the vendor redemption was created. The timestamp is in Epoch time format.           |  
| \*\*\`createdOnDateTime\`\*\*     | Indicates the date and time when the vendor redemption was created, formatted in ISO 8601\.                       |  
| \*\*\`lastUpdatedOnDateTime\`\*\* | Indicates the date and time when the vendor redemption was updated, formatted in ISO 8601\.                       |

\# API error codes

| Code | Description     | Reason                         |  
| :--- | :-------------- | :----------------------------- |  
| 3004 | Brand not found | \`brandId\` provided is invalid. |

\# OpenAPI definition  
\`\`\`json  
{  
  "\_id": "/branches/1.0/apis/v1.json",  
  "openapi": "3.1.0",  
  "info": {  
    "title": "v1",  
    "version": "1.0"  
  },  
  "servers": \[  
    {  
      "url": "https://{host}",  
      "variables": {  
        "host": {  
          "default": "host"  
        }  
      }  
    }  
  \],  
  "components": {  
    "securitySchemes": {  
      "sec0": {  
        "type": "http",  
        "scheme": "basic"  
      }  
    }  
  },  
  "security": \[  
    {  
      "sec0": \[\]  
    }  
  \],  
  "paths": {  
    "/api\_gateway/rewards/core/v1/vendor/{vendorId}/status/{action}/brand/{brandId}": {  
      "put": {  
        "summary": "Enable or Disable a Vendor",  
        "description": "",  
        "operationId": "enable-disable-vendor",  
        "parameters": \[  
          {  
            "name": "vendorId",  
            "in": "path",  
            "description": "Unique identifier of the vendor.",  
            "schema": {  
              "type": "integer",  
              "format": "int64"  
            },  
            "required": true  
          },  
          {  
            "name": "brandId",  
            "in": "path",  
            "description": "Unique identifier of the brand",  
            "schema": {  
              "type": "integer",  
              "format": "int32"  
            },  
            "required": true  
          },  
          {  
            "name": "action",  
            "in": "path",  
            "description": "Enable or disable the vendor.",  
            "schema": {  
              "type": "string",  
              "enum": \[  
                "enable",  
                "disable"  
              \]  
            },  
            "required": true  
          }  
        \],  
        "responses": {  
          "200": {  
            "description": "200",  
            "content": {  
              "application/json": {  
                "examples": {  
                  "Result": {  
                    "value": "{\\n    \\"status\\": {\\n        \\"success\\": true,\\n        \\"code\\": 5006,\\n        \\"message\\": \\"Vendor status updated successfully\\"\\n    },\\n    \\"vendorRo\\": {\\n        \\"id\\": 133,\\n        \\"name\\": \\"VENDORHIRE\\",\\n        \\"brandId\\": 61,\\n        \\"enabled\\": false,\\n        \\"isEncryptionRequired\\": false,\\n        \\"vendorTypes\\": null,\\n        \\"vendorDetails\\": null,\\n        \\"type\\": \\"REWARDS\\",\\n        \\"createdBy\\": 75161973,\\n        \\"lastUpdatedBy\\": 75161973,\\n        \\"createdOn\\": 1747307907000,\\n        \\"lastUpdatedOn\\": 1748350778000,\\n        \\"createdOnDateTime\\": \\"2025-05-15T11:18:27Z\\",\\n        \\"lastUpdatedOnDateTime\\": \\"2025-05-27T12:59:38Z\\",\\n        \\"rank\\": 1,\\n        \\"code\\": \\"Doc0036\\",\\n        \\"description\\": \\"The top priority vendor\\",\\n        \\"images\\": null,\\n        \\"videos\\": null,\\n        \\"encryptionRequired\\": false\\n    }\\n}"  
                  }  
                },  
                "schema": {  
                  "type": "object",  
                  "properties": {  
                    "status": {  
                      "type": "object",  
                      "properties": {  
                        "success": {  
                          "type": "boolean",  
                          "example": true,  
                          "default": true  
                        },  
                        "code": {  
                          "type": "integer",  
                          "example": 5006,  
                          "default": 0  
                        },  
                        "message": {  
                          "type": "string",  
                          "example": "Vendor status updated successfully"  
                        }  
                      }  
                    },  
                    "vendorRo": {  
                      "type": "object",  
                      "properties": {  
                        "id": {  
                          "type": "integer",  
                          "example": 133,  
                          "default": 0  
                        },  
                        "name": {  
                          "type": "string",  
                          "example": "VENDORHIRE"  
                        },  
                        "brandId": {  
                          "type": "integer",  
                          "example": 61,  
                          "default": 0  
                        },  
                        "enabled": {  
                          "type": "boolean",  
                          "example": false,  
                          "default": true  
                        },  
                        "isEncryptionRequired": {  
                          "type": "boolean",  
                          "example": false,  
                          "default": true  
                        },  
                        "vendorTypes": {},  
                        "vendorDetails": {},  
                        "type": {  
                          "type": "string",  
                          "example": "REWARDS"  
                        },  
                        "createdBy": {  
                          "type": "integer",  
                          "example": 75161973,  
                          "default": 0  
                        },  
                        "lastUpdatedBy": {  
                          "type": "integer",  
                          "example": 75161973,  
                          "default": 0  
                        },  
                        "createdOn": {  
                          "type": "integer",  
                          "example": 1747307907000,  
                          "default": 0  
                        },  
                        "lastUpdatedOn": {  
                          "type": "integer",  
                          "example": 1748350778000,  
                          "default": 0  
                        },  
                        "createdOnDateTime": {  
                          "type": "string",  
                          "example": "2025-05-15T11:18:27Z"  
                        },  
                        "lastUpdatedOnDateTime": {  
                          "type": "string",  
                          "example": "2025-05-27T12:59:38Z"  
                        },  
                        "rank": {  
                          "type": "integer",  
                          "example": 1,  
                          "default": 0  
                        },  
                        "code": {  
                          "type": "string",  
                          "example": "Doc0036"  
                        },  
                        "description": {  
                          "type": "string",  
                          "example": "The top priority vendor"  
                        },  
                        "images": {},  
                        "videos": {},  
                        "encryptionRequired": {  
                          "type": "boolean",  
                          "example": false,  
                          "default": true  
                        }  
                      }  
                    }  
                  }  
                }  
              },  
              "text/plain": {  
                "examples": {  
                  "Result": {  
                    "value": "{\\n    \\"status\\": {\\n        \\"success\\": true,\\n        \\"code\\": 5006,\\n        \\"message\\": \\"Vendor status updated successfully\\"\\n    }\\n}"  
                  }  
                },  
                "schema": {  
                  "type": "object",  
                  "properties": {  
                    "status": {  
                      "type": "object",  
                      "properties": {  
                        "success": {  
                          "type": "boolean",  
                          "example": true,  
                          "default": true  
                        },  
                        "code": {  
                          "type": "integer",  
                          "example": 5006,  
                          "default": 0  
                        },  
                        "message": {  
                          "type": "string",  
                          "example": "Vendor status updated successfully"  
                        }  
                      }  
                    }  
                  }  
                }  
              }  
            }  
          },  
          "400": {  
            "description": "400",  
            "content": {  
              "application/json": {  
                "examples": {  
                  "Result": {  
                    "value": "{}"  
                  }  
                },  
                "schema": {  
                  "type": "object",  
                  "properties": {}  
                }  
              }  
            }  
          }  
        },  
        "deprecated": false,  
        "x-readme": {  
          "code-samples": \[  
            {  
              "language": "curl",  
              "code": "curl \--location \--request PUT 'https://eu.api.capillarytech.com/api\_gateway/rewards/core/v1/vendor/5/status/disable/brand/3' \\\\\\n--header 'Accept: application/json' \\\\\\n--header 'Content-Type: application/json' \\\\\\n--header 'Authorization: Basic YXV0b3N0b3JlMS50aWxsMS0xNjgwMTY5MjIxOjIwMmNiOTYyYWM1OTA3NWI5NjRiMDcxNTJkMjM0Yjcw'"  
            }  
          \],  
          "samples-languages": \[  
            "curl"  
          \]  
        }  
      }  
    }  
  },  
  "x-readme": {  
    "headers": \[  
      {  
        "key": "Content-Type",  
        "value": "application/json"  
      },  
      {  
        "key": "Accept",  
        "value": "application/json"  
      }  
    \],  
    "explorer-enabled": true,  
    "proxy-enabled": true  
  },  
  "x-readme-fauxas": true  
}  
\`\`\`  
