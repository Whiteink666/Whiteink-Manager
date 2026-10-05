# 模块仓库格式

FurryRoot Manager 从本仓库读取模块数据：

- `modules.json` — 模块列表（必需）
- `module/<moduleId>.json` — 单个模块详情（可选，缺失时回退官方源）

## modules.json

顶层是数组，每项字段如下：

```json
[
  {
    "moduleId": "com.example.mod",
    "moduleName": "示例模块",
    "authors": [{ "name": "作者", "link": "https://github.com/someone" }],
    "summary": "一句话说明",
    "metamodule": false,
    "zygisk": false,
    "stargazerCount": 0,
    "updatedAt": "2026-10-06T00:00:00Z",
    "createdAt": "2026-10-06T00:00:00Z",
    "latestRelease": {
      "name": "v1.0",
      "time": "2026-10-06T00:00:00Z",
      "downloadUrl": "https://example.com/mod.zip",
      "versionCode": 1
    }
  }
]
```

要点：

- `moduleId` 必须与模块 `module.prop` 里的 id 一致，否则不会识别为已安装。
- `downloadUrl` 必须是一个可直接下载的 .zip（模块刷机包）。
- `versionCode` 用于判断是否有更新，递增即可。