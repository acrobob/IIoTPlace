# VSCode + PortableGit + GitHub 個人知識庫

## 一、PortableGit 基本概念

PortableGit 是免安裝版 Git。

適合場景：

- 公司無安裝權限
- USB 隨身攜帶
- 臨時開發環境
- 不想修改系統環境

典型路徑：

```text
C:\Users\acrobob.liu\Downloads\PortableGit
```

---

## 二、VSCode 無法辨識 Git 問題

如果 VSCode 出現：

```text
Download Git for Windows
```

代表：

```text
VSCode 找不到 git.exe
```

---

## 三、設定 VSCode git.path

開啟 User Settings JSON：

```text
Ctrl + Shift + P
Preferences: Open User Settings (JSON)
```

加入：

```json
{
  "git.path": "C:\\Users\\acrobob.liu\\Downloads\\PortableGit\\cmd\\git.exe"
}
```

Reload：

```text
Ctrl + Shift + P
Reload Window
```

---

## 四、VSCode Git 與 Terminal PATH 差異

`git.path` 只影響 VSCode Source Control Extension，不影響 PowerShell PATH。

所以可能 Source Control 正常，但 Terminal 顯示：

```powershell
git : The term 'git' is not recognized
```

這時可以直接用完整路徑：

```powershell
& "C:\Users\acrobob.liu\Downloads\PortableGit\cmd\git.exe" --version
```

---

## 五、第一次 Git 身份設定

```powershell
& "C:\Users\acrobob.liu\Downloads\PortableGit\cmd\git.exe" config --global user.name "acrobob"
& "C:\Users\acrobob.liu\Downloads\PortableGit\cmd\git.exe" config --global user.email "bobliu260@qq.com"
```

驗證：

```powershell
& "C:\Users\acrobob.liu\Downloads\PortableGit\cmd\git.exe" config --global --list
```

正常結果：

```text
user.name=acrobob
user.email=bobliu260@qq.com
```

---

## 六、Credential Helper

第一次 Push 時如果跳出 CredentialHelperSelector，建議選：

```text
manager
```

並勾選：

```text
Always use this from now on
```

### manager

推薦。支援 GitHub OAuth、Token 管理、VSCode 整合最好。

### wincred

舊版 Windows Credential，目前較少使用。

### no helper

每次 Push 都要重新輸入帳號密碼，不推薦。

---

## 七、Git Flow 基本架構

```text
main
develop
feature/*
hotfix/*
```

### main

正式穩定版，只放可部署、可上線版本。

### develop

開發主線，功能先合到這裡。

### feature/*

功能開發分支，例如：

```text
feature/dashboard
feature/login
feature/rabbitmq
feature/cfx-parser
```

### hotfix/*

正式版緊急修復，例如：

```text
hotfix/amqp-bug
```

---

## 八、Git Branch 基本操作

```bash
git branch
git checkout -b feature/login
git checkout main
git merge feature/login
```

VSCode 左下角的 branch 名稱也可以圖形化建立、切換、Merge branch。

---

## 九、推薦 Extension

必裝：

- GitLens
- Git Graph

推薦：

- GitHub Pull Requests
- Docker
- YAML
- REST Client

---

## 十、推薦專案結構

```text
IIoTPlace/
 ├── backend/
 ├── frontend/
 ├── deployment/
 ├── edge/
 ├── dashboard/
 ├── ai-agent/
 └── docs/
```

---

## 十一、推薦 .gitignore

```gitignore
__pycache__/
*.pyc
.venv/
.env
.vscode/
```

---

## 十二、Commit Message 習慣

不推薦：

```text
update
fix
123
```

推薦：

```text
feat: add Flask bootstrap
fix: repair Mongo query
docs: update deployment notes
refactor: split API service
```

---

## 十三、GitHub + Obsidian Knowledge Base 工作流

```text
ChatGPT
   ↓
Markdown
   ↓
GitHub Repo
   ↓
Obsidian Knowledge Base
```

---

## 十四、IIoT Knowledge Base 建議架構

```text
IIoT-KnowledgeBase/
 ├── 00_Inbox/
 ├── 01_Workplace/
 ├── 02_TMF/
 ├── 03_CFX/
 ├── 04_RabbitMQ/
 ├── 05_MongoDB/
 ├── 06_FastAPI/
 ├── 07_Streamlit/
 ├── 08_Deployment/
 ├── 09_Edge/
 ├── 10_Troubleshooting/
 ├── 11_SOP/
 ├── 12_MeetingNotes/
 ├── 13_AI_Agent/
 ├── diagrams/
 ├── assets/
 └── templates/
```

---

## 十五、技術文件 Template

```markdown
# Topic Name

## Purpose

## Architecture

## Flow

## Config

## Troubleshooting

## Reference
```

---

## 十六、SOP Template

```markdown
# SOP Name

## Scope

## Prerequisite

## Steps

## Validation

## Rollback

## Notes
```

---

## 十七、目前定位

這套不是單純筆記，而是：

```text
Engineering Knowledge System
```

包含：

- 技術沉澱
- SOP
- 架構設計
- Troubleshooting
- 團隊知識傳承
- 專案管理
- 平台部署
- DevOps Flow
