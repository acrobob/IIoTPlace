# IIoTPlace

IIoTPlace 是用來整理 IIoT 平台部署、Edge 服務、Kubernetes YAML、以及工程知識庫的專案。

目前內容包含：

- IIoT / microk8s 部署 YAML
- GitHub + VSCode + PortableGit 開發環境筆記
- 後續 Workplace / TMF / CFX / RabbitMQ / MongoDB / Edge Deployment 知識沉澱

---

## 目錄結構

```text
IIoTPlace/
 ├── README.md
 ├── iiot_stack_k8s.yaml
 └── docs/
     └── knowledge-base/
         └── vscode-git-portablegit.md
```

---

## 快速部署 IIoT Stack

### 1. 建立 iiot namespace

```bash
kubectl create namespace iiot
```

### 2. 部署 YAML 檔案

```bash
kubectl apply -f iiot_stack_k8s.yaml
```

### 3. 檢查 Pod 狀態

```bash
kubectl get pods -n iiot
```

### 4. 檢查 Service

```bash
kubectl get svc -n iiot
```

---

## Knowledge Base

技術知識庫放在：

```text
docs/knowledge-base/
```

目前已建立：

| 文件 | 說明 |
|---|---|
| `vscode-git-portablegit.md` | VSCode + PortableGit + GitHub 設定流程、Git Flow、Commit Message 習慣、Obsidian 知識庫方向 |

---

## 建議後續知識庫分類

```text
docs/
 ├── knowledge-base/
 ├── sop/
 ├── deployment/
 ├── troubleshooting/
 ├── architecture/
 └── meeting-notes/
```

---

## 推薦工作流

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

## 未來可沉澱內容

- Workplace Architecture
- TMF SOP
- CFX Topic Notes
- RabbitMQ Deployment
- MongoDB Query Examples
- FastAPI Backend Notes
- Streamlit Dashboard Notes
- Edge Device Operation
- microk8s Deployment
- Troubleshooting Cases
- GitHub Actions / CI-CD Flow

---

## Commit Message 建議

```text
feat: add new feature
fix: repair issue
docs: update documentation
refactor: improve code structure
chore: update config or tooling
```

---

## 目前定位

這個 Repo 不只是單純放 YAML，而是逐步整理成：

```text
IIoT Engineering Knowledge System
```

用來支援：

- 平台部署
- 技術文件
- SOP
- Troubleshooting
- 團隊知識傳承
- DevOps Flow
