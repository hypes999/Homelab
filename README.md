# Homelab com Ubuntu + VM Windows (XAMPP)

## Objetivo

Criar um ambiente de homelab em Ubuntu, utilizando o sistema como host principal e executando uma máquina virtual Windows com XAMPP para alojar um site. Este projeto serve para prática em redes, virtualização e administração de sistemas.

---

## Arquitetura Planeada

* **Host (bare metal):** Ubuntu 24.04.3 LTS
* **Hipervisor:** VMware Workstation Player
* **VM Windows 10:** com XAMPP e site em execução
* **Rede:** configuração Bridge para acesso local e remoto

---

## 🔧 Preparação

### Instalação do Ubuntu

1. Download do **Ubuntu 22.04.4 LTS ISO**
   <img width="1000" height="300" alt="imagem" src="https://github.com/user-attachments/assets/a48f363b-f85b-4cb0-9dc1-65010b6e7c85" />

3. Confirmar o SHA-256 da ISO para ver se o ficheiro está íntegro
   <img width="1000" height="300" alt="Captura de ecrã 2025-09-20 124146" src="https://github.com/user-attachments/assets/44563947-1430-449d-929f-f4e918d640a0" />

4. Criar pen bootável com o balenaEtcher
   <img width="1000" height="400" alt="imagem" src="https://github.com/user-attachments/assets/2e7c188e-c2a9-4b2d-adc4-1fa88049cc79" />
   <img width="1000" height="400" alt="imagem" src="https://github.com/user-attachments/assets/2d98ca61-1a47-4397-aca2-828b4c80b5de" />
   <img width="1000" height="400" alt="imagem" src="https://github.com/user-attachments/assets/f8d322f0-93b8-45cf-803a-5b20627d5b22" />


5. Instalar Ubuntu no host físico (disco dedicado)

---

## ⚙️ Execução

### Instalação do Hipervisor

Instalar VMware Workstation Player

### Importar a VM Windows

* No Virt-Manager: *Import existing disk image* → selecionar `.vmdk` ou `.vhdx`
* No VMware: *Open Virtual Machine* → selecionar `.vmx`

### Configuração de Rede

* Definir **Bridge** se precisar acesso direto na LAN
* Definir **NAT** se bastar acesso com partilha de internet

### Testes

* Arrancar VM Windows
* Verificar site no XAMPP → `http://<ip-da-vm>`

---

## Resultados

* VM Windows funcional no host Ubuntu
* Site acessível via rede
* Infraestrutura modular para expansão

---

## Próximos Passos

* Adicionar **pfSense** como firewall virtual
* Implementar **VPN (WireGuard/OpenVPN)**
* Integrar ferramentas de monitorização (Zabbix, Grafana, Prometheus)
* Documentar rede interna e segurança

---

## Notas de Documentação

* Este documento será atualizado conforme o progresso
* Screenshots, outputs de comandos e diagramas devem ser adicionados
