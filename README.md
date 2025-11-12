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

1. **Download da ISO**
   <img width="1680" height="265" alt="imagem" src="https://github.com/user-attachments/assets/c1b23f68-d4cb-434a-ab5a-30e3da07cc7c" />
   <img width="862" height="220" alt="imagem" src="https://github.com/user-attachments/assets/8ab5c5c7-c5d0-4fb2-83fd-e2547d118a23" />

3. **Criar pen bootável com o balenaEtcher**
   <img width="1018" height="466" alt="imagem" src="https://github.com/user-attachments/assets/229e2a06-69bc-4507-9e8d-ba2226a68bdc" />

5. **Instalação**  
   <img width="1919" height="786" alt="imagem" src="https://github.com/user-attachments/assets/36978951-185b-47dd-89a6-d2fbfed64795" />

#### Instalação e Configuração do Tailscale em LXC container mode

1. **Adicionar Debian 12 ao template de containers**
   <img width="1919" height="771" alt="imagem" src="https://github.com/user-attachments/assets/50a2d43d-9fb2-46d0-9878-68a49f6ca05e" />
2. **Download do OS**
   <img width="1024" height="455" alt="imagem" src="https://github.com/user-attachments/assets/c97fe2d7-9fb2-4553-82bb-c6091a356d9f" />
3. **Criação e Configuração do container LXC**
   <img width="1919" height="817" alt="imagem" src="https://github.com/user-attachments/assets/ae0c3640-b0de-4245-93e2-fc93f0437264" />
   <img width="915" height="274" alt="imagem" src="https://github.com/user-attachments/assets/004f559e-628a-4bd4-bbed-2c359df674c6" />
   <img width="915" height="687" alt="imagem" src="https://github.com/user-attachments/assets/8de1b981-61f4-49b6-b480-10156ddb068a" />
   <img width="920" height="162" alt="imagem" src="https://github.com/user-attachments/assets/d25dc7e6-5e65-4b54-bba7-6dbc54bb0aac" />
   <img width="913" height="191" alt="imagem" src="https://github.com/user-attachments/assets/44574b6f-ffd0-4055-9d19-1ece5ab95ddf" />
   <img width="914" height="686" alt="imagem" src="https://github.com/user-attachments/assets/8316e03c-e10b-4d5a-b4f3-9b020fe42d41" />
   <img width="906" height="684" alt="imagem" src="https://github.com/user-attachments/assets/e77a3c5b-64e7-4712-ae29-15e23a78b882" />
   <img width="1005" height="475" alt="imagem" src="https://github.com/user-attachments/assets/1e511ab6-c539-4cbf-94c0-8cb1ce4fb54e" />
   <img width="592" height="47" alt="imagem" src="https://github.com/user-attachments/assets/b40cb40b-3923-456b-ae39-4417a74438e8" />
   <img width="1919" height="793" alt="imagem" src="https://github.com/user-attachments/assets/1e57586e-be58-44d8-9028-116f83cb5d92" />
4. **Configuração e Instalação do Tailscale**
   <img width="764" height="42" alt="imagem" src="https://github.com/user-attachments/assets/aaee3a30-81ab-4772-9706-0d855bb3a105" />
   <img width="1360" height="275" alt="imagem" src="https://github.com/user-attachments/assets/bb1ebe0f-7aae-49bb-9788-3a80e13cf5cf" />
   <img width="621" height="123" alt="imagem" src="https://github.com/user-attachments/assets/2db70e23-a96c-4910-9b63-c2f830dcd3e1" />

5. **IP Forwarding**
   <img width="1351" height="316" alt="imagem" src="https://github.com/user-attachments/assets/ac8ec45a-2293-4e9a-9931-d77cc5c8ed3b" />
6. **Exit Node**
   <img width="1336" height="96" alt="imagem" src="https://github.com/user-attachments/assets/5ce3d0b1-5937-4a86-a09a-09cbb6af8a50" />
   <img width="658" height="547" alt="imagem" src="https://github.com/user-attachments/assets/cd8d9fe2-7f38-47f1-922d-8e828d4c7bce" />

#### Instalação e Configuração do Pi-Hole

1. Criar container LXC no Proxmox
   <img width="906" height="679" alt="imagem" src="https://github.com/user-attachments/assets/a2b9e2c5-a184-47d3-a1d9-1ac275538736" />
   <img width="913" height="682" alt="imagem" src="https://github.com/user-attachments/assets/cc45efbc-6d63-4f0c-99e0-b4f528cd8ba1" />
   <img width="913" height="672" alt="imagem" src="https://github.com/user-attachments/assets/447fe9e5-3946-41ae-827e-6b3c0ce9fbef" />
   <img width="1001" height="486" alt="imagem" src="https://github.com/user-attachments/assets/99423856-c89d-46b4-a9ea-18009c3cc943" />
2. Instalação do Pi-Hole
   <img width="817" height="734" alt="imagem" src="https://github.com/user-attachments/assets/d6c24524-2c32-4a1f-9083-13462b96d1f0" />
   <img width="811" height="468" alt="imagem" src="https://github.com/user-attachments/assets/b5972fb5-0fb8-45ab-8bfd-6f0e7e8ea63a" />
   <img width="798" height="467" alt="imagem" src="https://github.com/user-attachments/assets/c6246c42-3f87-47a1-b535-46054a21add2" />
   <img width="786" height="462" alt="imagem" src="https://github.com/user-attachments/assets/3fa7f353-aa6d-4026-a389-e1accfa164a2" />
   <img width="795" height="471" alt="imagem" src="https://github.com/user-attachments/assets/1112018d-655a-4c8b-b8fe-8fed1921a108" />
   <img width="634" height="169" alt="imagem" src="https://github.com/user-attachments/assets/70d8e401-50c4-4484-b4c7-4cf4c89d4e69" />
   <img width="657" height="533" alt="imagem" src="https://github.com/user-attachments/assets/8fc2a6c2-9616-44be-9f69-3143dc3ed67d" />


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

### HTTPS
<img width="961" height="420" alt="imagem" src="https://github.com/user-attachments/assets/4c67dc41-cd68-499c-8f16-313465ef4db5" />

### DNS Foward
<img width="958" height="259" alt="imagem" src="https://github.com/user-attachments/assets/61d2ed34-d4f8-4ad7-afd0-8c01fa849d3d" />

### Fail2Ban + UFW
<img width="867" height="740" alt="imagem" src="https://github.com/user-attachments/assets/4d831c1b-87de-4ad6-a400-0adc2a51a0fb" />




---

## Notas de Documentação

- Este documento será atualizado conforme o progresso.
- Screenshots, outputs de comandos e diagramas devem ser adicionados.
