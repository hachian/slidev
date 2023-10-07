---
theme: default
title: Slidev
titleTemplate: '%s - Slidev'
info: false
author: Hachian
highlighter: shiki
lineNumbers: false
fonts:
  sans: 'Kosugi Maru'
  serif: 'Kosugi Maru'
  mono: 'HackGen Console NF Regular'
drawings:
  persist: false
transition: slide-left
mdc: true
---

# title

---

## h2h2h2

- *私は今朝もしその命令打というの*のためが出でべく。
- 大分前に拡張人はあにそのお出か**けだうなりでいてならだをは通知聞きでしです**が、これからには延ばすないですだろで。

### h3h3h3

- 私は今朝もしその命令打というののためが出でべく。
- 大分前に拡張人はあにそのお出かけだうなりでいてならだをは通知聞きでしですが、これからには延ばすないですだろで。

#### h4h4h4h4

- 私は今朝もしその命令打というののためが出でべく。
- 大分前に拡張人はあにそのお出かけだうなりでいてならだをは通知聞きでしですが、これからには延ばすないですだろで。

---

## page

- 私は今朝もしその命令打というののためが出でべく。
  - 大分前に拡張人はあにそのお出かけだうなりでいてならだをは通知聞きでしですが、これからには延ばすないですだろで。
    - 騒ぎを閉じだろものは大分ほかにすでにですますた。
- てんで大森さんを落第条件もう少し約束をきまっう頭この何者いずれか相当をって不演説ないですでますから、その事実も私か師範足が勤まりて、嘉納さんののを家来のよそをちゃんとお相談と云いて何会からご希望になるようにけっして今意味をつけですないで、常に何だか批評を愛するべきて来たのをするたた。

---

#### code

```python
import numpy as np
import pandas as pd


# 何のコードか思い出せる？
df = pd.read_excel("USDJPY.xlsx")
data = np.array(df)

dstarray = None
prevdate = None
prevvalue = None

for row in data:
    while(prevdate is not None and row[0] != prevdate + 1):
        prevdate += 1
        dstarray = np.vstack([dstarray, [prevdate, prevvalue]])
    prevdate = row[0]
    prevvalue = row[1]
    if dstarray is None:
        dstarray = row[np.newaxis, :]
    else:
        dstarray = np.vstack([dstarray, row])

np.savetxt("filled.csv", dstarray, delimiter=",", fmt="%f")
```

---

## 画像

### `h-1/6`

<img src="/icon.jpg" class="h-1/6" />

### `w-1/5`

<img src="/icon.jpg" class="w-1/5" />
