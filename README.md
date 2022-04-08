
# github-action-json-property

![Banner image showing successfully executed GitHub Action](banner.png)

Get a specified property of a json file.

## Usage

### Use the action inside your workflow yaml file like this:

```yaml
...
- name: get version
  id: version
  uses: dotnetthailand/actions-json-get-key@v1
  with: 
    path: 'package.json'
    prop_path: 'version'
- run: echo ${{steps.version.outputs.prop}} 
...

```


### Get a nested property value with dot separated prop_path 

```yaml
...
- name: get nested property
  id: format_script
  uses: dotnetthailand/actions-json-get-key@v1
  with: 
    path: 'package.json'
    prop_path: 'scripts.format'
- run: echo ${{steps.format_script.outputs.prop}} 
...

```

### Export the value to file

```yaml
...
- name: get nested property
  id: format_script
  uses: dotnetthailand/actions-json-get-key@v1
  with: 
    path: 'package.json'
    prop_path: 'scripts.format'
    output_path: 'version.txt'
- run: cat version.txt
...

```

Thanks the original: https://github.com/notiz-dev/github-action-json-property