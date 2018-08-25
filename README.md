# Elastic APM Java agent Role

Ansible role for downloading and configuring Elastic APM Java agent. Primarily
used for shipping logs and metrics to an ELK stack. This role creates the ```elasticapm.properties```
file with the default values defined.


Role Variables
--------------
#### Default installation values

```yaml
elastic_apm_java_agent_version: 0.6.2
elastic_apm_java_agent_download_location: "https://repo1.maven.org/maven2"
elastic_apm_java_agent_download_url: "{{ elastic_apm_java_agent_download_location }}/co/elastic/apm/elastic-apm-agent/{{ elastic_apm_java_agent_version }}/elastic-apm-agent-{{ elastic_apm_java_agent_version }}.jar"
elastic_apm_java_agent_dir: "/opt/elastic-apm-agent"
elastic_apm_java_agent_filename: "elastic-apm-agent-{{ elastic_apm_java_agent_version }}.jar"
```

#### Configuration

The default values are already installed in the ```elasticapm.properties``` file.
If you need to define variables or overwrite any default, you should use the ```elastic_apm_java_agent_conf``` variable
as shown below:

```yaml
elastic_apm_java_agent_conf:
    service_name: my-service
    service_version: 1.0.0
    server_url: http://my-server:8200
``` 

The full list of available options can be found here: [https://www.elastic.co/guide/en/apm/agent/java/current/index.html](https://www.elastic.co/guide/en/apm/agent/java/current/index.html)

License
-------

GNU GPLv3