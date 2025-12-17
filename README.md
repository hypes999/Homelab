# Homelab Proxmox VE

## Objetivo

Criar um ambiente de homelab no Proxmox VE, utilizando o sistema como host principal e executando vários serviços. Este projeto serve para prática em redes, virtualização e administração de sistemas.

---

## Arquitetura

- **Host (bare metal):** Proxmox VE 9.0.1
- **Hipervisor:** VMware Workstation Player
- **VM Windows 10:** com XAMPP e site em execução
- **Rede:** configuração Bridge para acesso local e remoto

---

## Preparação

### Instalação do Proxmox VE

#### 1. Download da ISO
![Download ISO](https://github.com/user-attachments/assets/c1b23f68-d4cb-434a-ab5a-30e3da07cc7c)
![ISO Selection](https://github.com/user-attachments/assets/8ab5c5c7-c5d0-4fb2-83fd-e2547da118a23)

#### 2. Criar Pen Bootável com BalenaEtcher
![BalenaEtcher](https://github.com/user-attachments/assets/229e2a06-69bc-4507-9e8d-ba2226a68bdc)

#### 3. Processo de Instalação
![Instalação Proxmox](https://github.com/user-attachments/assets/36978951-185b-47dd-89a6-d2fbfed64795)

---

## Tailscale em LXC Container

### Preparação do Ambiente

#### 1. Adicionar Debian 12 ao Template
![Template Debian](https://github.com/user-attachments/assets/50a2d43d-9fb2-46d0-9878-68a49f6ca05e)

#### 2. Download do Sistema Operacional
![Download OS](https://github.com/user-attachments/assets/c97fe2d7-9fb2-4553-82bb-c6091a356d9f)

### Criação do Container LXC

#### 3. Configuração do Container
![Configuração Container](https://github.com/user-attachments/assets/ae0c3640-b0de-4245-93e2-fc93f0437264)
![Configuração Rede](https://github.com/user-attachments/assets/004f559e-628a-4bd4-bbed-2c359df674c6)
![Configuração DNS](https://github.com/user-attachments/assets/8de1b981-61f4-49b6-b480-10156ddb068a)
![Confirmação Configuração](https://github.com/user-attachments/assets/d25dc7e6-5e65-4b54-bba7-6dbc54bb0aac)
![Instalação](https://github.com/user-attachments/assets/44574b6f-ffd0-4055-9d19-1ece5ab95ddf)
![Container Criado](https://github.com/user-attachments/assets/8316e03c-e10b-4d5a-b4f3-9b020fe42d41)
![Console Container](https://github.com/user-attachments/assets/e77a3c5b-64e7-4712-ae29-15e23a78b882)
![Interface Web](https://github.com/user-attachments/assets/1e511ab6-c539-4cbf-94c0-8cb1ce4fb54e)
![Status Container](https://github.com/user-attachments/assets/b40cb40b-3923-456b-ae39-4417a74438e8)
![Container Ativo](https://github.com/user-attachments/assets/1e57586e-be58-44d8-9028-116f83cb5d92)

### Instalação do Tailscale

#### 4. Configuração e Instalação
![Comandos Instalação](https://github.com/user-attachments/assets/aaee3a30-81ab-4772-9706-0d855bb3a105)
![Processo Instalação](https://github.com/user-attachments/assets/bb1ebe0f-7aae-49bb-9788-3a80e13cf5cf)
![Autenticação](https://github.com/user-attachments/assets/2db70e23-a96c-4910-9b63-c2f830dcd3e1)

#### 5. Configuração de IP Forwarding
![IP Forwarding](https://github.com/user-attachments/assets/ac8ec45a-2293-4e9a-9931-d77cc5c8ed3b)

#### 6. Configuração como Exit Node
![Exit Node Config](https://github.com/user-attachments/assets/5ce3d0b1-5937-4a86-a09a-09cbb6af8a50)
![Dashboard Tailscale](https://github.com/user-attachments/assets/cd8d9fe2-7f38-47f1-922d-8e828d4c7bce)

---

## Instalação do Pi-Hole

### Criação do Container

#### 1. Configuração do Container LXC
![Criação Container](https://github.com/user-attachments/assets/a2b9e2c5-a184-47d3-a1d9-1ac275538736)
![Configuração Template](https://github.com/user-attachments/assets/cc45efbc-6d63-4f0c-99e0-b4f528cd8ba1)
![Configuração Disco](https://github.com/user-attachments/assets/447fe9e5-3946-41ae-827e-6b3c0ce9fbef)
![Container Finalizado](https://github.com/user-attachments/assets/99423856-c89d-46b4-a9ea-18009c3cc943)

### Instalação do Pi-Hole

#### 2. Processo de Instalação
![Instalação Pi-Hole](https://github.com/user-attachments/assets/d6c24524-2c32-4a1f-9083-13462b96d1f0)
![Configuração Rede](https://github.com/user-attachments/assets/b5972fb5-0fb8-45ab-8bfd-6f0e7e8ea63a)
![Seleção DNS](https://github.com/user-attachments/assets/c6246c42-3f87-47a1-b535-46054a21add2)
![Configuração Blocklists](https://github.com/user-attachments/assets/3fa7f353-aa6d-4026-a389-e1accfa164a2)
![Configuração Web Interface](https://github.com/user-attachments/assets/1112018d-655a-4c8b-b8fe-8fed1921a108)
![Instalação Completa](https://github.com/user-attachments/assets/70d8e401-50c4-4484-b4c7-4cf4c89d4e69)
![Interface Web Pi-Hole](https://github.com/user-attachments/assets/8fc2a6c2-9616-44be-9f69-3143dc3ed67d)

### Testes e Resultados

#### 3. Verificação de Funcionamento
![Testes DNS](https://github.com/user-attachments/assets/2aedc7a9-e732-4775-bee7-f4be242ded02)
![Estatísticas Pi-Hole](https://github.com/user-attachments/assets/ffd7df4d-1178-491a-a135-78a041a4466f)

---

## Instalação do NextCloud

### Instalação Automatizada

#### 1. Instalação via Script Proxmox VE
![Instalação NextCloud](https://github.com/user-attachments/assets/e13c917e-b66a-4a6d-93a7-7c8cd65bfaa3)

**Comando utilizado:**
```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/community-scripts/ProxmoxVE/main/ct/nextcloudpi.sh)"
```

### Configuração do NextCloud

#### 2. Acesso e Interface
![Acesso NextCloud](https://github.com/user-attachments/assets/7c6e74e7-6f7c-42ae-b84e-adf9a1b2b356)
![Interface NextCloud](https://github.com/user-attachments/assets/c30b59d8-0776-438d-9f96-baaf5fd5f057)

---

## Instalação do Nginx Proxy Manager

1. Instalação e Configuração do Docker Container
   <img width="1919" height="788" alt="imagem" src="https://github.com/user-attachments/assets/b15acff4-72ee-4c7e-b226-28b1b7e9f0b8" />
   <img width="1919" height="972" alt="imagem" src="https://github.com/user-attachments/assets/64caab32-cc3d-427f-85de-92c6fc90dd3d" />
   
## Instalação do Vaultwarden

1. Instalação e Configuração do LXC com Script automático
   <img width="1919" height="826" alt="imagem" src="https://github.com/user-attachments/assets/38b1ca4d-472f-4507-ae48-a2eea0916280" />
   <img width="1919" height="931" alt="imagem" src="https://github.com/user-attachments/assets/b651f0e1-b1d7-457a-8121-67f2e8fdfa95" />

## Instalação do QBitTorrent

1. Instalação e Configuração do LXC com Script automático
   <img width="1919" height="782" alt="imagem" src="https://github.com/user-attachments/assets/c64cfc1b-da8f-4846-aff6-b0559759ec14" />
   <img width="1919" height="945" alt="imagem" src="https://github.com/user-attachments/assets/597b059c-3f5f-47bf-aec2-888bffc9a0c6" />

## Instalação do Wordpress

1. Instalação e Configuração do LXC com Script automático
   <img width="1919" height="810" alt="imagem" src="https://github.com/user-attachments/assets/96433aa8-c531-427b-a022-856593e8e526" />


## Instalação do Actual Budget

1. Instalação e Configuração do LXC com Script automático
   <img width="1919" height="791" alt="imagem" src="https://github.com/user-attachments/assets/ebc643b8-66ba-4758-a3a1-b6667a3e3d5f" />

## Instalação do Glance

1. Instalação e Configuração do LXC com Script automático
   <img width="1919" height="775" alt="imagem" src="https://github.com/user-attachments/assets/ec672e02-c5f6-4108-9d88-43b0210dd3bf" />


## Resultados

- VM Windows funcional no host Ubuntu
- Site acessível via rede
- Infraestrutura modular para expansão

---

## Notas de Documentação

- Este documento será atualizado conforme o progresso.
- Screenshots, outputs de comandos e diagramas devem ser adicionados.
