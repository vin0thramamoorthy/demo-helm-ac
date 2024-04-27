# Helm Template Functions and Pipelines

# Functions
1. Template Actions `{{ }}`
2. Action Elements `{{ .Release.Name }}`
3. Quote Function
4. Pipeline 
5. default Function
6. lower function
7. Controlling White Spaces `{{-  -}}`
7. indent function
8. nindent function
9. toYaml
10. if, else, eq, and 
# and Syntax
and .Arg1 .Arg2 = both true = true
11. if, else, eq, or
or .Arg1 .Arg2 = if any one is true = true
12. if, else, eq, not
13. Flow Control action with
14. variable -- {{- $chartname := .Chart.Name | quote | upper -}}
15. Flow Control action range

