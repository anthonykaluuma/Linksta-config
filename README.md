[![Gem Version](https://badge.fury.io/rb/linksta.svg)](https://badge.fury.io/rb/linksta)

# Linksta 

**Status checker for your websites**

Check a page for broken links by doing a status check on all the relative URL's on the page.

## Usage

```s
gem install linksta 
```

### Command Line

```sh
linksta smoke /path/to/config.yaml
```

**Examples**

```sh
linksta smoke configs/live.yaml
```

**Output**

Once running, you'll see either a 200 with `Status is 200 for <URL>` or `Status is NOT GOOD for <URL>`.

### Config File

In some situations, you may be deploying applications that you don't want to be public facing, so ensuring they don't 200 is essential.  There is a status code option to allow a specific status code to be set against a group of URL's, ensuring builds fail if the right code conditions are met.

Example YAML Config:

```yaml
base: 'http://www.foo.co.uk'

headers:
  -
   key: 'X-content-override'
   value: 'https://example.com'

statuscode: 200

paths:
  - /foo
  - /foo/new

```
