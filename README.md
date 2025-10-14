# Homelab com Ubuntu + VM Windows (XAMPP)

## Objetivo

Criar um ambiente de homelab em Ubuntu, utilizando o sistema como host principal e executando uma máquina virtual Windows com XAMPP para alojar um site. Este projeto serve para prática em redes, virtualização e administração de sistemas.

---

## Arquitetura

* **Host (bare metal):** Ubuntu 22.04.5 LTS
* **Hipervisor:** VMware Workstation Player
* **VM Windows 10:** com XAMPP e site em execução
* **Rede:** configuração Bridge para acesso local e remoto

---

## 🔧 Preparação

### Instalação do Ubuntu

1. Download do **Ubuntu 22.04.4 LTS ISO**
  <img width="1266" height="76" alt="imagem" src="https://github.com/user-attachments/assets/98cf3e07-023e-4d8d-89f5-09b4606a81f1" />

2. Confirmar o SHA-256 da ISO para ver se o ficheiro está íntegro
   <img width="1518" height="193" alt="imagem" src="https://github.com/user-attachments/assets/07e66fad-0748-42bc-99b9-fd55371be957" />

3. Criar pen bootável com o balenaEtcher
   <img width="1000" height="400" alt="imagem" src="https://github.com/user-attachments/assets/2e7c188e-c2a9-4b2d-adc4-1fa88049cc79" />
   <img width="1000" height="400" alt="imagem" src="https://github.com/user-attachments/assets/2d98ca61-1a47-4397-aca2-828b4c80b5de" />
   <img width="1000" height="400" alt="imagem" src="https://github.com/user-attachments/assets/f8d322f0-93b8-45cf-803a-5b20627d5b22" />


4. Instalar Ubuntu no host físico (disco dedicado)
  <img width="1757" height="986" alt="imagem" src="https://github.com/user-attachments/assets/fb93be55-887f-4da1-b5e0-47a3454b1b6d" />


---

## ⚙️ Execução

### Instalação do Hipervisor
Instalar VMware Workstation Player 

### Importar a Máquina

Préviamente já criada e configurada

<img width="1037" height="844" alt="imagem" src="https://github.com/user-attachments/assets/4df5027c-61b4-443f-9896-fe961bb1524e" />

* Definir **Bridge** para acesso direto na LAN

<img width="794" height="390" alt="imagem" src="https://github.com/user-attachments/assets/324c7842-9fca-41a6-83db-ae1dc641568b" />

### Testes

* Arrancar VM Windows
* Verificar IP's
  <img width="1635" height="536" alt="imagem" src="https://github.com/user-attachments/assets/86ba814b-a3e9-41e2-879b-4f77b3080ff2" />

* Start dos serviços essenciais: Apache e MySQL
  <img width="629" height="441" alt="imagem" src="https://github.com/user-attachments/assets/a4563017-d901-41d1-a835-4da176d39cb5" />
* Verificar Cloudflare
  <img width="1919" height="550" alt="imagem" src="https://github.com/user-attachments/assets/cfd34483-5dd5-472a-ab77-f1124294e8f6" />

---

## Resultados

* VM Windows funcional no host Ubuntu
* Site acessível via rede
* Infraestrutura modular para expansão

---

## Próximos Passos

* Implementar **VPN**
* Documentar rede interna e segurança

---

## Notas de Documentação

* Este documento será atualizado conforme o progresso
* Screenshots, outputs de comandos e diagramas devem ser adicionados
