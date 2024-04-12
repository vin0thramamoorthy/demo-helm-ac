# demo-helm-ac
Helm's template language provides the following control structures:

If/else — for creating conditional blocks
with — to specify a scope
range — which provides a “for each”-style loop

In this article, we will discuss helm flow control along with various examples.

If/else
We can control the flow of the helm chart using the If/else statement just like any other programming language.

{{ if PIPELINE }}
  # Do something
{{ else if OTHER PIPELINE }}
  # Do something else
{{ else }}
  # Default case
{{ end }}

A pipeline will be evaluated as false if the value is:

a boolean false
a numeric zero
an empty string
a nil (empty or null)
an empty collection (map, slice, tuple, dict, array)

Now, Let’s see how we can use if/else in a helm template.

Suppose, we have values.yaml file with the following entries :

# values.yaml
configMap:
  data:
    mode: dark
    env: test

And now we will create a configmap.yaml template file, where we will use if/else for decision-making purposes:

apiVersion: v1
kind: ConfigMap
metadata:
  name: {{ .Release.Name }}-configmap
data:
  {{ if .Values.configMap.data.darkMode }}          # boolean check
  mode: dark
  {{ else }}
  mode: light
  {{ end }}
  {{ if eq .Values.configMap.data.env "prod"  }}    # string check
  env: prod
  {{ else if eq .Values.configMap.data.env "dev" }}
  env: dev
  {{ else }}
  env: test
  {{ end }}