# 玻璃基板供應鏈追蹤系統

IC 設計工程師視角的玻璃基板（Glass Substrate）供應鏈研究與每週動態追蹤工具。

## 專案目的

追蹤玻璃基板取代 ABF 有機載板的產業趨勢，涵蓋：

- **技術路線**：FOPLP / FOWLP / TGV / CoPoS
- **供應鏈層次**：材料（Tier 1）→ 設備（Tier 2）→ 基板製造（Tier 3）
- **關鍵廠商**：欣興（3037）、鈦昇、群翊（6664）、弘塑（3131）、辛耘（3583）、台積電 CoPoS、群創 FOPLP

## 檔案結構

```
glass-substrate/
├── glass-substrate-supply-chain.docx   # 供應鏈基礎研究報告
├── glass-substrate-track.md            # 每週追蹤 Agent Prompt 模板
├── 玻璃基板_weekly_update_YYYY-MM-DD.md # 每週追蹤報告（依日期命名）
├── glass_to_docx.py                    # Markdown → DOCX 轉換工具
└── build_docx.py                       # DOCX 建構腳本
```

## 每週追蹤流程

`glass-substrate-track.md` 為 Claude Code Agent Prompt，每週一執行：

1. 搜尋最近 7 天產業新發展（Firecrawl 優先，Playwright 備用）
2. 建立候選來源清單（官網 IR > 官方文件 > 媒體報導）
3. 擷取內容並與上週基準比對
4. 產出 Markdown 週報（`玻璃基板_weekly_update_YYYY-MM-DD.md`）
5. 寄送 Email 摘要至研究者信箱

## 追蹤重點

| 類別 | 關注指標 |
|------|---------|
| 技術進度 | CoPoS 試產線、TGV 良率、翹曲解決方案 |
| 量產時程 | 台積電 CoPoS 2028 最早、群創 FOPLP 1-2 年 |
| 競爭格局 | 中國 JCET + Huawei Tau Law 生態系進展 |
| 投資訊號 | 欣興 EPS、鈦昇月營收、設備廠訂單動態 |

## 執行環境

- Claude Code（含 Firecrawl MCP、Playwright MCP、Gmail MCP）
- Python 3.x（DOCX 轉換用）

```bash
python glass_to_docx.py
```

---

*資料僅供研究參考，不構成投資建議*
