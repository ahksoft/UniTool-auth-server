# UniTool Unified MediaTek Auth & Loader Server (`mtk` branch)

Single unified MediaTek server serving **both** **UniTool-MTK** (device templates via `meta.json`) and **mtkclient / Auto-Loader** (SoC HW-code auto-matching via `index.json`) from one deduplicated repository.

## Branch Layout

```
mtk/
├── meta.json                  # Device Templates index (Brand -> Model -> DA / Auth / Preloader)
├── index.json                 # Auto-Loader & mtkclient index (hwcode -> DA / Auth / Preloader / Payload)
├── meta/<vendor>/<codename>.meta.yml
├── files/                     # Deduplicated MTK V5/V6 DAs & SV5/SV6 .auth files
├── files/Preloader/           # Deduplicated device preloaders (shared by meta.json & index.json)
├── files/payloads/            # Stage-1 BROM exploit payloads (mtkclient)
└── .github/scripts/merge_meta.py
```

## Endpoints

- **Device Templates (UniTool-MTK):**
  `https://raw.githubusercontent.com/ahksoft/UniTool-auth-server/mtk/meta.json`
- **Auto-Loader / mtkclient Index:**
  `https://raw.githubusercontent.com/ahksoft/UniTool-auth-server/mtk/index.json`

## Current Inventory

- **Device Templates (`meta.json`):** 365 devices across 15 brands
- **DA Loaders (`index.json`):** 139
- **Auth Files (`index.json`):** 31
- **Preloaders (`index.json`):** 1083
- **BROM Payloads (`index.json`):** 61

| Brand | Device Templates |
|---|---:|
| Asus | 5 |
| Huawei | 24 |
| Infinix | 38 |
| Itel | 5 |
| Lenovo | 1 |
| Meizu | 1 |
| Motorola | 6 |
| Nothing | 2 |
| OnePlus | 7 |
| Oppo | 73 |
| Realme | 8 |
| Samsung | 28 |
| Tecno | 8 |
| Vivo | 56 |
| Xiaomi | 103 |

## Other Platform Branches in This Repo

- `qualcomm` — Qualcomm Firehose programmers (ELF/MBN) + EDL XML operation scripts
- `spd` — Unisoc / Spreadtrum FDL1 & FDL2 loaders with load addresses
- `testpoints` — Hardware EDL / BROM / VBAT testpoint reference gallery
