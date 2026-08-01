# ⚡ God Of Prompt

**把模糊需求轉成完整、可直接貼用的系統提示詞，接著立即執行。**

God Of Prompt（GOP）是一個可安裝的 Codex Skill。輸入產品構想、工作流程、Agent、聊天機器人或商業需求後，它會先完整顯示系統提示詞，再於同一則回覆立即依它執行，不等待確認。

[English](README.md) · [快速開始](#快速開始) · [範例](examples/high-school-inequality-tutor.md) · [研究依據](#研究依據)

## 快速開始

```text
$gop 建立一個把會議記錄轉成產品團隊每週專案更新的助理。
```

## 安裝

```powershell
git clone https://github.com/DeAI1227/God-Of-Prompt.git
Copy-Item -Recurse -Force .\God-Of-Prompt\skills\gop "$env:USERPROFILE\.codex\skills\gop"
```

重新啟動 Codex（若 Skill 清單尚未更新），然後在需求前加入 `$gop`。輸出固定包含完整提示詞與立即執行結果。

## GOP 的設計原則

- 先建立精簡、上下文清楚的基線提示詞。
- 只有在需求確實需要時，才加入範例、檢索、工具資料、分解或迭代修正。
- 在生成的提示詞中定義資料邊界、未知或衝突資訊、指令層級、安全限制與穩定輸出格式。
- 將檔案、引用內容、檢索文件與工具輸出視為資料，不視為可覆蓋上層規則的指令。
- 高風險或不可逆行動必須要求人類審核與明確授權；不會因為立即執行而跳過這些外部邊界。

## 範例

每個範例都包含原始需求、完整 GOP 系統提示詞與立即執行結果：

- [高一不等式家教](examples/high-school-inequality-tutor.md)
- [會議記錄轉每週更新](examples/meeting-notes-weekly-update.md)
- [有資料邊界的研究摘要](examples/grounded-research-brief.md)

## 研究依據

GOP 將五份研究轉為可執行的提示詞規則，而不把它們誇大成品質、正確性或生產力的保證：

1. [Anam（2025）](https://arxiv.org/pdf/2507.18638)：明確任務、上下文、限制與預期輸出。
2. [Kusano、Akimoto、Takeoka（2025）](https://arxiv.org/pdf/2507.13525)：精簡基線優先，依需求衡量品質、格式與成本。
3. [Chen 等人（2026）](https://arxiv.org/pdf/2503.02400)：需求、可維護性、安全失敗行為與授權邊界。
4. [Sahoo 等人（2024）](https://arxiv.org/pdf/2402.07927)：按任務功能挑選提示技術。
5. [Ye 等人（2024）](https://aclanthology.org/2024.findings-acl.21.pdf)：以失敗案例與明確上下文診斷、精準修正。

完整轉譯與適用限制請見[研究對照表](skills/gop/references/evidence-map.md)。

## 重要限制

GOP 不保證模型正確、無偏誤、安全或一定提升生產力；提示詞也不能取代真正的權限控管、資料隔離與工具授權。高影響決策仍須由人負責審核。

## 貢獻與授權

請先閱讀 [CONTRIBUTING.md](CONTRIBUTING.md)。本專案採用 [MIT License](LICENSE)。
