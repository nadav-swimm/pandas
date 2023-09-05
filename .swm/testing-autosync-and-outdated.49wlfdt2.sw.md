---
id: 49wlfdt2
title: Testing autosync and outdated
file_version: 1.1.3
app_version: 1.16.4
---

`test_gold_canyon(self,`<swm-token data-swm-token=":pandas/tests/io/test_html.py:662:3:6:`    def test_gold_canyon(self, banklist_data):`"/>

<br/>

<br/>

> ddd

## title

<!-- empty line --><br/>
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 scripts/no_bool_in_generic.py
```python
39                 if isinstance(value, ast.AST):
40                     nodes.append((next_in_annotation, value))
41                 elif isinstance(value, list):
42                     for value in reversed(value):
43                         if isinstance(value, ast.AST):
```

<br/>


<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 scripts/no_bool_in_generic.py
```python
74         parser.add_argument("paths", nargs="*")
```

<br/>


<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 setup.cfg
```ini
107        # single-letter variables
```

<br/>


<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 scripts/validate_min_versions_in_sync.py
```python
1      #!/usr/bin/env python3
2      """
3      Check pandas required and optional dependencies are synced across:
4      
5      ci/deps/actions-.*-minimum_versions.yaml
6      pandas/compat/_optional.py
7      
8      TODO: doc/source/getting_started/install.rst
9      
10     This is meant to be run as a pre-commit hook - to run it manually, you can do:
11     
12         pre-commit run validate-min-versions-in-sync --all-files
13     """
14     from __future__ import annotations
15     
16     import pathlib
17     import sys
18     
19     DOC_PATH = pathlib.Path("doc/source/getting_started/install.rst").resolve()
20     CI_PATH = next(
21         pathlib.Path("ci/deps").absolute().glob("actions-*-minimum_versions.yaml")
22     )
23     CODE_PATH = pathlib.Path("pandas/compat/_optional.py").resolve()
24     # pandas package is not available
25     # in pre-commit environment
26     sys.path.append("pandas/compat")
27     sys.path.append("pandas/util")
28     import version
29     
30     sys.modules["pandas.util.version"] = version
31     import _optional
32     
33     
34     def get_versions_from_code() -> dict[str, str]:
35         install_map = _optional.INSTALL_MAPPING
36         versions = _optional.VERSIONS
37         return {
38             install_map.get(k, k).casefold(): v
39             for k, v in versions.items()
40             if k != "pytest"
41         }
42     
43     
44     def get_versions_from_ci(content: list[str]) -> tuple[dict[str, str], dict[str, str]]:
45         # Don't parse with pyyaml because it ignores comments we're looking for
46         seen_required = False
47         seen_optional = False
48         required_deps = {}
49         optional_deps = {}
50         for line in content:
51             if "# required dependencies" in line:
52                 seen_required = True
53             elif "# optional dependencies" in line:
54                 seen_optional = True
55             elif seen_required and line.strip():
56                 package, version = line.strip().split("=")
57                 package = package[2:]
58                 if not seen_optional:
59                     required_deps[package] = version
60                 else:
61                     optional_deps[package] = version
62         return required_deps, optional_deps
63     
64     
65     def main():
66         with open(CI_PATH, encoding="utf-8") as f:
67             _, ci_optional = get_versions_from_ci(f.readlines())
68         code_optional = get_versions_from_code()
69         diff = set(ci_optional.items()).symmetric_difference(code_optional.items())
70         if diff:
71             sys.stdout.write(
72                 f"The follow minimum version differences were found between  "
73                 f"{CI_PATH} and {CODE_PATH}. Please ensure these are aligned: "
74                 f"{diff}\n"
75             )
76             sys.exit(1)
77         sys.exit(0)
78     
79     
80     if __name__ == "__main__":
81         main()
82     
```

<br/>

;klj;klhj

<br/>

lkjlkjlkj;klj;
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
<!-- NOTE-swimm-repo ::dummy-repo:: -->
### 📄 examples/backbone/js/views/app-view.js
```javascript
13     		// Instead of generating a new element, bind to the existing skeleton of
14     		// the App already present in the HTML.
15     		el: '.todoapp',
16     
17     		// Our template for the line of statistics at the bottom of the app.
18     		statsTemplate: _.template($('#stats-template').html()),
19     
20     		// Delegated events for creating new items, and clearing completed ones.
21     		events: {
```

<br/>

<!--MERMAID {width:25}-->
```mermaid

```
<!--MCONTENT {content: "<br/>"} --->

<br/>

graph TD A\[Enter Chart Definition\] --> B(Preview) B --> C{decide} C --> D\[Keep\] C --> E\[Edit Definition\] E --> B D --> F\[Save Image and Code\] F --> Bblah
<!-- NOTE-swimm-snippet: the lines below link your snippet to Swimm -->
### 📄 codecov.yml
```yaml
8        status:
9          project:
10           default:
11             target: '82'
12         patch:
13           default:
```

<br/>

<br/>

<br/>

This file was generated by Swimm. [Click here to view it in the app](https://app.swimm.io/repos/Z2l0aHViJTNBJTNBcGFuZGFzJTNBJTNBbmFkYXYtc3dpbW0=/docs/49wlfdt2).
