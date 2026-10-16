# 壁纸图库

FurryRoot Manager 的在线背景图库。Manager 会读取本目录下的 `index.json`，把里面的图片列在「设置 → 背景」里供选择。

## 添加一张壁纸

1. 把图片文件放进本目录（支持 jpg / png / webp，建议长边 1080~2160，单张不超过 2MB）
2. 在 `index.json` 的 `wallpapers` 数组里加一项：

```json
{
  "id": "aurora",
  "name": "极光",
  "file": "aurora.jpg",
  "author": "可选，作者名",
  "source": "可选，原图链接"
}
```

字段说明：

| 字段 | 必填 | 说明 |
| --- | --- | --- |
| `id` | 是 | 唯一标识，只能用字母、数字、`-`、`_`；用作本地缓存文件名 |
| `name` | 是 | 列表里显示的名字 |
| `file` | 是 | 本目录下的文件名 |
| `author` | 否 | 作者，显示在名字下方 |
| `source` | 否 | 原图出处链接 |

## 删除壁纸

删掉图片文件，并把 `index.json` 里对应的项移除即可。用户本机已缓存的副本会在下次打开背景列表时清理。

图片地址最终拼成：
`https://raw.githubusercontent.com/Whiteink666/Whiteink-Manager/main/wallpapers/<file>`