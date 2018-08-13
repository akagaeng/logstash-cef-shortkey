# Logstash Plugin

This is CEF codec plugin for Logstash **with short extension key**. Since original CEF codec translate extension keys into known field names, I made new plugin without changing key names.

This will make a custom plugin named `logstash-codec-cef_shortkey`.

## How to use
1. Generate gem file
```
$ docker-compose run devenv
```

```
[root@devenv-jruby master] /storage
# gem build logstash-codec-cef_shortkey.gemspec
# exit
```

2. (optional) Remove pre-installed plugin

```
bin/logstash-plugin remove logstash-codec-cef_shortkey
```

3. Install plugin

```
bin/logstash-plugin install logstash-codec-cef_shortkey-0.1.0-java.gem
```

4. Restart Logstash

```
input { stdin{ codec => cef_shortkey{}} }
```

### reference
- https://www.elastic.co/guide/en/logstash/current/plugins-codecs-cef.html
- https://github.com/logstash-plugins/logstash-codec-cef
- https://www.elastic.co/guide/en/logstash/current/_how_to_write_a_logstash_codec_plugin.html