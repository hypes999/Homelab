# Homelab com Ubuntu + VM Windows (XAMPP)

## Objetivo

Criar um ambiente de homelab em Ubuntu, utilizando o sistema como host principal e executando uma máquina virtual Windows com XAMPP para alojar um site. Este projeto serve para prática em redes, virtualização e administração de sistemas.

---

## Arquitetura

- **Host (bare metal):** Ubuntu 22.04.5 LTS
- **Hipervisor:** VMware Workstation Player
- **VM Windows 10:** com XAMPP e site em execução
- **Rede:** configuração Bridge para acesso local e remoto

---

## 🔧 Preparação

### Instalação do Ubuntu

1. **Download do Ubuntu 22.04.4 LTS ISO**  
  ![Download Ubuntu](https://github.com/user-attachments/assets/98cf3e07-023e-4d8d-89f5-09b4606a81f1)

2. **Confirmar o SHA-256 da ISO**  
  ![SHA-256 Ubuntu](https://github.com/user-attachments/assets/07e66fad-0748-42bc-99b9-fd55371be957)

3. **Criar pen bootável com o balenaEtcher**  
  ![balenaEtcher 1](https://github.com/user-attachments/assets/2e7c188e-c2a9-4b2d-adc4-1fa88049cc79)  
  ![balenaEtcher 2](https://github.com/user-attachments/assets/2d98ca61-1a47-4397-aca2-828b4c80b5de)  
  ![balenaEtcher 3](https://github.com/user-attachments/assets/f8d322f0-93b8-45cf-803a-5b20627d5b22)

4. **Instalar Ubuntu no host físico (disco dedicado)**  
  ![Instalação Ubuntu](https://github.com/user-attachments/assets/fb93be55-887f-4da1-b5e0-47a3454b1b6d)

---

## ⚙️ Execução

### Instalação do Hipervisor

Instalar VMware Workstation Player.

### Importar a Máquina

Préviamente já criada e configurada.

![Importar VM](https://github.com/user-attachments/assets/4df5027c-61b4-443f-9896-fe961bb1524e)

- Definir **Bridge** para acesso direto na LAN

![Configuração Bridge](https://github.com/user-attachments/assets/324c7842-9fca-41a6-83db-ae1dc641568b)

### Testes

- Arrancar VM Windows
- Verificar IPs  
  ![Verificar IP](https://github.com/user-attachments/assets/86ba814b-a3e9-41e2-879b-4f77b3080ff2)

- Start dos serviços essenciais: Apache e MySQL  
  ![Apache e MySQL](https://github.com/user-attachments/assets/a4563017-d901-41d1-a835-4da176d39cb5)

- Verificar Cloudflare  
  ![Cloudflare](https://github.com/user-attachments/assets/cfd34483-5dd5-472a-ab77-f1124294e8f6)

---

## Resultados

- VM Windows funcional no host Ubuntu
- Site acessível via rede
- Infraestrutura modular para expansão

---

## Próximos Passos

- Implementar **VPN**
- Documentar rede interna e segurança

---

## Tailscale

### Instalação e Inicialização

![Tailscale 1](https://github.com/user-attachments/assets/7eb0968f-0333-49d1-9f9e-fe452bfdf3fd)  
![Tailscale 2](https://github.com/user-attachments/assets/b8fe2bc8-6312-4401-a031-99ded964d274)  
![Tailscale 3](https://github.com/user-attachments/assets/c2a2ddea-fd9d-4fdf-8c3d-3d29b94cca5b)

### Ativar o modo "exit node" para IP público

[Referência YouTube](https://www.youtube.com/watch?v=Ad7D2pkFNdA)  
![Exit Node 1](https://github.com/user-attachments/assets/463d32f6-9da7-4394-90fb-f5263edf5a58)  
![Exit Node 2](https://github.com/user-attachments/assets/64ffef65-f1c4-4685-b6e3-c1351530ce7c)  
![Exit Node 3](https://github.com/user-attachments/assets/d84eebbd-f9cf-41db-9e09-9d6c8e1efa3b)

### Permitir acesso à LAN local

![LAN Local 1](https://github.com/user-attachments/assets/0e6c6d5f-0116-4e1c-a889-29c3b8e3b09d)  
![LAN Local 2](https://github.com/user-attachments/assets/63ec8be6-84b2-4b5a-9a30-fc2739760b5d)

### Ativar o IP Forwarding

![IP Forwarding 1](https://github.com/user-attachments/assets/117e254f-ef84-44b9-9037-4a64b235a59d)  
![IP Forwarding 2](https://github.com/user-attachments/assets/4b5bea9c-3ec2-4e8f-8c29-9bf3e855455b)  
![IP Forwarding 3](https://github.com/user-attachments/assets/e6d7e640-8319-4ede-bc29-6ecd249b9257)  
![IP Forwarding 4](https://github.com/user-attachments/assets/7b95dd40-bba0-48d0-be81-07ea12d7eca9)  
![IP Forwarding 5](https://github.com/user-attachments/assets/1e9ca96c-323a-48dd-ae59-1143a9943db7)  
![IP Forwarding 6](https://github.com/user-attachments/assets/a1449ff4-634a-4db8-a3e9-173584b71e7b)

### Desativar o Generic Receive Offload (GRO) apenas para packets forwarders

![GRO 1](https://github.com/user-attachments/assets/9dce7795-204e-41b1-a580-d71397f4c25b)  
![GRO 2](https://github.com/user-attachments/assets/fa123dfa-5480-4afc-8648-702908d10168)  
![GRO 3](https://github.com/user-attachments/assets/369570c4-f52d-4c59-a59d-68b8475135f8)

### Desativar a Expiração da chave

![Expiração Chave 1](https://github.com/user-attachments/assets/eb51acde-2eea-4d16-b9a0-e3853fe697b7)  
![Expiração Chave 2](https://github.com/user-attachments/assets/c4bfb714-26a3-4e35-b659-efc611392f0a)  
![Expiração Chave 3](https://github.com/user-attachments/assets/adaf815a-3c00-4804-860b-9e7f21635267)  
![Expiração Chave 4](https://github.com/user-attachments/assets/ee99504a-fe94-484b-b9b9-98014df9629d)

## NextCloud

### Instalação
<img width="958" height="339" alt="imagem" src="https://github.com/user-attachments/assets/1385226f-04d5-4e89-b659-3e2808032ff5" />
<img width="869" height="262" alt="imagem" src="https://github.com/user-attachments/assets/d7cfcf37-c79b-47c1-a1d1-a908e1ecfa92" />
<img width="959" height="361" alt="imagem" src="https://github.com/user-attachments/assets/14d9daa9-e441-4d58-afc0-07c2bf8cfc89" />
<img width="958" height="404" alt="imagem" src="https://github.com/user-attachments/assets/b323d791-62ac-4502-866a-54ca769b8600" />
<img width="959" height="136" alt="imagem" src="https://github.com/user-attachments/assets/ae72daf4-995a-4a3a-9108-1df161dac9a0" />
<img width="1289" height="960" alt="imagem" src="https://github.com/user-attachments/assets/12166c3e-7894-46bb-a243-0295f1403339" />



---

## Notas de Documentação

- Este documento será atualizado conforme o progresso.
- Screenshots, outputs de comandos e diagramas devem ser adicionados.
