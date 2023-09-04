---
title: QA'ing Mermaid Diagram on the new editor
---
&nbsp;

&nbsp;

```mermaid
sequenceDiagram
    User Interface->>+Git CLI: git add
    Git CLI->>+User Interface: John, can you hear me?
    Git CLI-->>chdir: If RUN_SETUP in commands
    chdir-->>Git CLI: 
    Note right of Git CLI: prefix gets the path to the subdir
    Git CLI->>Command (add): prefix
    Command (add)->>Git CLI: return code
    Git CLI->>+User Interface: return code
```

<SwmMeta repo-id="Z2l0aHViJTNBJTNBcGFuZGFzJTNBJTNBbmFkYXYtc3dpbW0=" repo-name="pandas"><sup>Powered by [Swimm](http://localhost:5001/)</sup></SwmMeta>
