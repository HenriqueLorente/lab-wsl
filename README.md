# 🐧 Lab WSL – Docker + Terraform + Git + VS Code

Este repositório contém um **mini-laboratório** rodando em **WSL2 (Ubuntu no Windows)** para aprender e praticar:

- Docker + Docker Compose
- Terraform (provider docker)
- Git + GitHub (fluxo de branches e pull requests)
- Integração com VS Code

---

## 📂 Estrutura do projeto


lab-wsl/
│
├── docker/
│ ├── docker-compose.yml # Sobe um container Nginx via Compose
│ └── html/ # Arquivos HTML servidos pelo Nginx (porta 8080)
│
├── terraform/
│ └── main.tf # Provisiona container Nginx via Terraform (porta 8081)
│
└── .gitignore

---

## ▶️ Como rodar localmente

### Subir via Docker Compose
```bash
cd docker
docker compose up -d
# acessar em http://localhost:8080

cd terraform
terraform init
terraform apply -auto-approve
# acessar em http://localhost:8081

cd docker && docker compose down
cd terraform && terraform destroy -auto-approve

Fluxo de contribuição (GitHub Flow)

Para manter o histórico limpo e organizado, o fluxo usado é baseado em branches + Pull Requests:

Criar uma branch a partir da main
git checkout main
git pull origin main
git checkout -b feat/nova-secao


Fazer as alterações no código
code docker/html/index.html
git add .
git commit -m "feat(web): adicionar nova seção ao site"

git push -u origin feat/nova-secao
Abrir um Pull Request

No GitHub, abra o PR da branch feat/nova-secao para main

Revise e faça o merge

Atualizar sua main local
git checkout main
git pull origin main

Objetivo

Esse repositório é usado como laboratório para:

Praticar versionamento com Git/GitHub

Testar pipelines simples com Docker + Terraform

Melhorar o fluxo de desenvolvimento e contribuição
