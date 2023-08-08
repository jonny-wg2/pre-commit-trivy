# pre-commit-trivy

[pre-commit](https://pre-commit.com) hooks for Trivy

## Example:
Add the hooks to your .pre-commit-config.yaml like so:

```yaml
  - repo: https://github.com/jonny-wg2/pre-commit-trivy
    rev: v0.1.0
    hooks:
      - id: trivyfs-docker
        exclude: ".+test.+$|.+presentations.+$"
        args:
          - --severity 
          - HIGH,CRITICAL
          - . # last arg indicates the path/file to scan
        stages: [manual]
      - id: trivyconfig-docker
        exclude: ".+test.+$|.+presentations.+$"
        args:
          - --severity 
          - CRITICAL
          - . # last arg indicates the path/file to scan
        stages: [manual]
```
