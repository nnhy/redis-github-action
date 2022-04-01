<div align="center">
  <p>
    <h3>Redis in GitHub Actions</h3>
  </p>
  <p>启动一个Redis，用于单元测试</p>
</div>

---

## 简介

使用docker容器启动一个Redis实例，用于自动化单元测试。

## 用法

```yaml
name: test

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Git checkout
        uses: actions/checkout@v2
  
      - name: Setup EMQ
        uses: nnhy/redis-github-action@v1.0
  
      - name: Test
        run: dotnet test -c Release XUnitTestClient/XUnitTestClient.csproj
```
