# PMD Source Code Analyzer Action (Fix)

This action allows to use PMD Source Code Analyzer from GitHub Actions and fixes a small issue regarding permissions. It is forked from 
[https://github.com/sfdx-actions/setup-pmd](https://github.com/sfdx-actions/setup-pmd). Check his action out. Most of the documentation will remain the same. 

## Example usage

```yaml
name: PMD Source Code Analyzer on Push

on: [push]

jobs:
  pmd:
  
    runs-on: ubuntu-latest
    
    steps:
      - name: Setup JRE
        uses: actions/setup-java@v1
        with:
          java-version: '13.0.2'
          java-package: jre
          architecture: x64

      - uses: ashkumar-wtc/setup-pmd@v1
      - name: run-pmd
        run: pmd -d <source code> -R <ruleset> -f xml --failOnViolation false > report.xml
```

## License
```
MIT License

Copyright (c) 2019 Felipe Echanique Torres (felipe.echanique at gmail.com)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
