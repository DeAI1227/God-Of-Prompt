# ⚡ God Of Prompt

**把模糊需求轉成可檢查、可直接貼用的專家級 XML 系統提示詞，接著立即執行。**

God Of Prompt（GOP）是一個可安裝的 Codex Skill。它採用六段式架構：**Starter → Context → Task → Examples → Output → Repeat**。GOP 會先顯示完整提示詞，再於同一則回覆直接執行，不等待確認。

[English](README.md) · [快速開始](#快速開始) · [架構說明](docs/architecture.md) · [範例](#範例) · [推廣工具包](docs/launch-playbook.md)

## 快速開始

```text
$gop 建立一個把會議記錄轉成產品團隊每週專案更新的助理。
```

輸出固定只有兩節：`完整 System Prompt`，接著是`執行結果`。不會額外要求你確認提示詞。

## 安裝

```powershell
git clone https://github.com/DeAI1227/God-Of-Prompt.git
Copy-Item -Recurse -Force .\God-Of-Prompt\skills\gop "$env:USERPROFILE\.codex\skills\gop"
```

重新啟動 Codex（若 Skill 清單尚未更新），然後在需求前加入 `$gop`。

## GOP v0.2 提示詞架構

| 區段 | 負責的事情 |
|---|---|
| `starter` | 一到兩句任務定位；只有角色會改變觀點或標準時才使用。 |
| `context` | 只放會改變判斷的使用者、事實、輸入與邊界。 |
| `task` | 可執行工作、`MUST` / `SHOULD` / `MAY`、驗收條件與失敗處理。 |
| `examples` | 具代表性的示範；不需要時明確寫出不使用示範。 |
| `output` | 輸出容器、欄位、順序、長度、證據與資訊不足時的行為。 |
| `repeat` | 最重要的一到兩條提醒，避免重複堆字。 |

提示詞採 XML，讓每個區塊可讀、可查、可測。它不是為了變長：GOP 先建立最小可行的六段式基線，只有需求真的需要時才加入技術。

## 有條件使用技術，而不是裝飾

- few-shot 範例必須先檢查數量、順序、標籤分布、標籤品質、格式與相似度。
- 有實質歧義時才進行精簡的任務重述；只有安全完成被阻擋時才問一個精準問題。
- 真正多跳的工作才做任務分解；只呈現使用者要求或輸出真正需要的檢查點，不索取隱藏思維鏈。
- 使用外部資料時，必須宣告授權來源、新鮮度、衝突、歸因與不確定性規則。
- 重複失敗時才診斷失敗維度、最多做三次聚焦修正，並以保留案例評估。

## 範例

每個範例皆包含原始需求、六段式 GOP 系統提示詞與立即執行結果：

- [高一不等式家教](examples/high-school-inequality-tutor.md)
- [會議記錄轉每週更新](examples/meeting-notes-weekly-update.md)
- [有資料邊界的研究摘要](examples/grounded-research-brief.md)

## 依據與限制

GOP 以維護者提供的研習 PDF 為主架構，並用五篇論文補上：明確任務與上下文、精簡基線、受控技術選擇、Promptware 生命週期，以及從失敗案例驗證修正。完整內容請見[研究對照表](skills/gop/references/evidence-map.md)。

這不代表保證生產力、正確性、安全、公平或消除幻覺。提示詞也不能取代真正的權限控管、資料隔離、祕密管理、工具授權、監控與人類負責機制。

## 貢獻與授權

請先閱讀 [CONTRIBUTING.md](CONTRIBUTING.md)。本專案採用 [MIT License](LICENSE)。
