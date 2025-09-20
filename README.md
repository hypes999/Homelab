# Homelab com Ubuntu + VM Windows (XAMPP)

## 📌 Objetivo

Criar um ambiente de homelab em Ubuntu, utilizando o sistema como host principal e executando uma máquina virtual Windows com XAMPP para alojar um site. Este projeto serve para prática em redes, virtualização e administração de sistemas.

---

## 🗂 Arquitetura Planeada

* **Host (bare metal):** Ubuntu 22.04 LTS
* **Hipervisor:** KVM/QEMU (Virt-Manager) ou VMware Workstation Player
* **VM Windows 10:** com XAMPP e site em execução
* **Rede:** configuração NAT/Bridge para acesso local e remoto

---

## 🔧 Preparação

### Instalação do Ubuntu

1. Download do **Ubuntu 22.04 LTS ISO**
<img width="1725" height="331" alt="imagem" src="https://github.com/user-attachments/assets/a48f363b-f85b-4cb0-9dc1-65010b6e7c85" />

2. Criar pen bootável com Rufus ou balenaEtcher
3. Instalar Ubuntu no host físico (disco dedicado)

---

## ⚙️ Execução

### Instalação do Hipervisor

* **Opção A (recomendada):**

  ```bash
  sudo apt update && sudo apt install qemu-kvm libvirt-daemon-system virt-manager -y
  ```
* **Opção B:** instalar VMware Workstation Player

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

## ✅ Resultados

* VM Windows funcional no host Ubuntu
* Site acessível via rede
* Infraestrutura modular para expansão

---

## 🚀 Próximos Passos

* Adicionar **pfSense** como firewall virtual
* Implementar **VPN (WireGuard/OpenVPN)**
* Integrar ferramentas de monitorização (Zabbix, Grafana, Prometheus)
* Documentar rede interna e segurança

---

## 📖 Notas de Documentação

* Este documento será atualizado conforme o progresso
* Screenshots, outputs de comandos e diagramas devem ser adicionados
