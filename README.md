# K8s connector payloads for NG Rest Api

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

``` bash
curl -i -X POST \
  'https://app.harness.io/gateway/ng/api/connectors?accountIdentifier=YpUfe9mVQECwIhopss9sVw' \
  -H 'Content-Type: application/json' \
  -H 'x-api-key: sat.6217769197a451498fb0e9ab.iECo7J4RBxOH32tlhO9Q' \
  -d '{"connector": {"name": "API","identifier": "API","description": "API","orgIdentifier": "default","projectIdentifier": "Test_Project","tags": {"property1": "tempe"},"type": "K8sCluster","spec": {"credential": { "type": "InheritFromDelegate", "spec": null },"delegateSelectors": ["next-gen"]}}}'

```
# Artifactory connector payloads for NG Rest Api

#### Artifactory connector with auth
```JSON
{
  "connector": {
    "name": "Artifactory Jfrog",
    "identifier": "Artifactory_Jfrog",
    "description": "",
    "orgIdentifier": "default",
    "projectIdentifier": "Artifactory_Project",
    "tags": {},
    "type": "Artifactory",
    "spec": {
      "artifactoryServerUrl": "https://pedroharnesstest.jfrog.io/artifactory/",
      "auth": {
        "type": "UsernamePassword",
        "spec": {
          "username": "username",
          "usernameRef": null,
          "passwordRef": "JFROG_Pass"
        }
      },
      "delegateSelectors": []
    }
  }
}
```

#### Artifactory connector with no auth
``` JSON
{
    "connector": {
      "name": "Artifactory Jfrog",
      "identifier": "Artifactory_Jfrog",
      "description": "",
      "orgIdentifier": "default",
      "projectIdentifier": "Artifactory_Project",
      "tags": {},
      "type": "Artifactory",
      "spec": {
        "artifactoryServerUrl": "https://pedroharnesstest.jfrog.io/artifactory/",
        "auth": { "type": "Anonymous" },
        "delegateSelectors": []
      }
    }
}
```

# Jira connector payloads for NG Rest Api


#### Artifactory connector with plaintext auth
```JSON
{
  "connector": {
    "name": "Jira Test",
    "identifier": "Jira_Test",
    "description": "",
    "orgIdentifier": "default",
    "projectIdentifier": "Artifactory_Project",
    "tags": {},
    "type": "Jira",
    "spec": {
      "jiraUrl": "teste.com",
      "username": "user",
      "usernameRef": null,
      "passwordRef": "org.tst",
      "delegateSelectors": []
    }
  }
}
```

#### Artifactory connector with encrypted auth

```JSON
{
  "connector": {
    "name": "Jira Test",
    "identifier": "Jira_Test",
    "description": "",
    "orgIdentifier": "default",
    "projectIdentifier": "Artifactory_Project",
    "tags": {},
    "type": "Jira",
    "spec": {
      "jiraUrl": "teste.com",
      "username": null,
      "usernameRef": "org.tst",
      "passwordRef": "org.tst",
      "delegateSelectors": []
    }
  }
}
```
