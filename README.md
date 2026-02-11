# Homelab – Proxmox VE | Self-Hosted Infrastructure

## Overview

Este repositório documenta a conceção, implementação e evolução de um homelab baseado em **Proxmox VE**, focado em self-hosting, networking, segurança, automação e observabilidade.

O objetivo principal é:

- Demonstrar competências práticas em infraestrutura Linux
- Simular ambientes reais de produção
- Consolidar conhecimentos em virtualização, containers, redes e serviços
- Servir como portfolio técnico para contexto profissional

Todo o ambiente foi desenhado com preocupações reais de:

- Isolamento lógico
- Minimização de superfície de ataque
- Zero port-forwarding (CGNAT-safe)
- Logging centralizado
- Evolução incremental para arquitetura SOC-like

## Base Infrastructure

- **Hypervisor**: Proxmox VE
- **Virtualization**: LXC (unprivileged) + VM (Kali Linux – attack lab)
- **Networking**: Linux bridge (vmbr0)
- **Subnet**: 192.168.0.0/24
- **Gateway**: 192.168.0.1
- **DNS**: Pi-hole (192.168.0.30)
- **Public Exposure**: Cloudflare Tunnel (sem portas abertas)
- **Remote Access**: Tailscale (overlay VPN)

Todos os serviços críticos utilizam IPs fixos, evitando dependência de DHCP dinâmico.

## Logical Architecture

<img width="4134" height="3412" alt="imagem" src="https://github.com/user-attachments/assets/84da9afc-6d39-48d5-a098-abac0b820385" />

## Services Inventory

| Service     | CT ID | IP Address     | Description                                       |
| ----------- | ----- | -------------- | ------------------------------------------------- |
| Pi-hole     | 100   | 192.168.0.30   | DNS filtering / internal resolver                 |
| NextcloudPi | 101   | 192.168.0.40   | Self-hosted cloud                                 |
| Wazuh       | 102   | 192.168.0.200  | SIEM / Security monitoring                        |
| WordPress   | 105   | 192.168.0.100  | Public-facing application (via Cloudflare Tunnel) |
| cloudflared | 106   | 192.168.0.13   | Cloudflare Tunnel connector                       |
| Tailscale   | 1000  | 192.168.0.25   | VPN mesh node                                     |

## Virtual Machines

| VM         | Network       | Purpose                                 |
| ---------- | ------------- | --------------------------------------- |
| Kali Linux | DHCP (bridge) | Offensive simulation / attack scenarios |

## Exposure Model

- Nenhuma porta aberta no router
- Sem port forwarding
- Exposição pública feita exclusivamente via Cloudflare Tunnel
- Ambiente compatível com CGNAT
- Acesso administrativo remoto apenas via Tailscale

## Security Stack

### Wazuh (SIEM)
Instalado em LXC dedicado:

- Log collection
- File Integrity Monitoring
- Rootcheck
- Rule engine
- Alert correlation
- MITRE ATT&CK mapping

**Agents planeados / em expansão para**:
- WordPress
- Nextcloud
- Proxmox host
- Kali

## External Infrastructure – Oracle Free Tier

Alguns workloads são executados fora do homelab local, usando **Oracle Free Tier**, nomeadamente:

- OpenVPN Access Server
- Experimentos com LLM tooling (ex: LLM Council)

**Motivo**:

- Reduzir pressão de RAM no host local
- Simular arquiteturas híbridas (on-prem + cloud)
- Explorar troubleshooting real em cloud networking

## Technical Decisions (Why)

- **LXC em vez de VM**: menor overhead, melhor densidade
- **Glance em vez de Heimdall**: config declarativa e simples
- **ActualBudget**: controlo financeiro sem integração bancária
- **Oracle Free Tier**: workloads externos sem custo
- **IPs fixos**: previsibilidade e debug mais fácil

## Roadmap

- Domínio próprio
- HTTPS com Nginx Proxy Manager
- VPN gateway dedicado
- Media automation refinada
- Backups automatizados
- Observabilidade avançada
- LLM Council em produção (Oracle)

## Purpose

Este homelab representa experiência prática real, ainda que fora de contexto profissional formal.

Cada serviço foi instalado, configurado, testado e depurado manualmente.

O foco é aprendizagem profunda, não apenas “ter serviços a correr”.
