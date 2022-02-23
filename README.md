# K8s connector payloads for NG Rest Api

## Example payloads for K8s connectors when using NextGen Rest-API https://harness.io/docs/api/tag/Connectors

#### K8s connector with Inherited From Delegate auth
```JSON
{
  "connector": {
    "name": "K8s Connector",
    "identifier": "K8s_Connector",
    "description": "",
    "orgIdentifier": "default",
    "projectIdentifier": "Test_Project",
    "tags": {},
    "type": "K8sCluster",
    "spec": {
      "credential": { "type": "InheritFromDelegate", "spec": null },
      "delegateSelectors": ["next-gen"]
    }
  }
}
```

#### K8s connector with Username/Password auth
```JSON
{
  "connector": {
    "name": "K8s Connector",
    "identifier": "K8s_Connector",
    "description": "",
    "orgIdentifier": "default",
    "projectIdentifier": "Test_Project",
    "tags": {},
    "type": "K8sCluster",
    "spec": {
      "credential": {
        "type": "ManualConfig",
        "spec": {
          "masterUrl": "test.com",
          "auth": {
            "type": "UsernamePassword",
            "spec": {
              "username": "test",
              "usernameRef": null,
              "passwordRef": "GKE_SA"
            }
          }
        }
      },
      "delegateSelectors": []
    }
  }
}
```

#### K8s connector with ServiceAccount auth
```JSON
{
  "connector": {
    "name": "K8s Connector",
    "identifier": "K8s_Connector",
    "description": "",
    "orgIdentifier": "default",
    "projectIdentifier": "Test_Project",
    "tags": {},
    "type": "K8sCluster",
    "spec": {
      "credential": {
        "type": "ManualConfig",
        "spec": {
          "masterUrl": "test.com",
          "auth": {
            "type": "UsernamePassword",
            "spec": {
              "username": "test",
              "usernameRef": null,
              "passwordRef": "GKE_SA"
            }
          }
        }
      },
      "delegateSelectors": []
    }
  }
}
```

#### K8s connector with OpenIdConnect auth
```JSON
{
  "connector": {
    "name": "K8s Connector",
    "identifier": "K8s_Connector",
    "description": "",
    "orgIdentifier": "default",
    "projectIdentifier": "Test_Project",
    "tags": {},
    "type": "K8sCluster",
    "spec": {
      "credential": {
        "type": "ManualConfig",
        "spec": {
          "masterUrl": "test.com",
          "auth": {
            "type": "OpenIdConnect",
            "spec": {
              "oidcIssuerUrl": "test.com",
              "oidcUsername": "user",
              "oidcUsernameRef": null,
              "oidcClientIdRef": "GKE_SA",
              "oidcPasswordRef": "GKE_SA",
              "oidcSecretRef": "GKE_SA",
              "oidcScopes": "test_scope"
            }
          }
        }
      },
      "delegateSelectors": []
    }
  }
}

```

#### K8s connector with ClientKeyCert auth
```JSON
{
  "connector": {
    "name": "K8s Connector",
    "identifier": "K8s_Connector",
    "description": "",
    "orgIdentifier": "default",
    "projectIdentifier": "Test_Project",
    "tags": {},
    "type": "K8sCluster",
    "spec": {
      "credential": {
        "type": "ManualConfig",
        "spec": {
          "masterUrl": "test.com",
          "auth": {
            "type": "ClientKeyCert",
            "spec": {
              "caCertRef": "GKE_SA",
              "clientCertRef": "GKE_SA",
              "clientKeyRef": "GKE_SA",
              "clientKeyPassphraseRef": "GKE_SA",
              "clientKeyAlgo": "RSA"
            }
          }
        }
      },
      "delegateSelectors": []
    }
  }
}
```

## Notes

#### When the payload variable has **Ref** as a suffix, it means that it is a reference to an existing secret in Harness Platform (the variable **clientKeyPassphraseRef**, for example).
