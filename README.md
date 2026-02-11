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
- **Virtualization**: LXC (unprivileged)
- **Networking**: Linux bridge (vmbr0)
- **Subnet**: 192.168.0.0/24
- **Gateway**: 192.168.0.1
- **DNS**: Pi-hole
- **Dashboard**: Glance
- **Reverse Proxy**: Nginx Proxy Manager (preparado para HTTPS futuro)

Todos os serviços críticos utilizam IPs fixos, evitando dependência de DHCP dinâmico.

## Logical Architecture

<img width="4134" height="3412" alt="imagem" src="https://github.com/user-attachments/assets/84da9afc-6d39-48d5-a098-abac0b820385" />


## Services Inventory

| Service              | CT ID | IP Address     | Port(s) | Description             |
|----------------------|-------|----------------|---------|-------------------------|
| Proxmox VE Host      | -     | 192.168.0.20   | 8006    | Hypervisor              |
| Pi-hole              | 100   | 192.168.0.30   | 80      | DNS / Ad blocking       |
| Nextcloud            | 101   | 192.168.0.40   | 80      | Personal cloud          |
| qBittorrent          | 102   | 192.168.0.75   | 8090    | Downloads               |
| Vaultwarden          | 103   | 192.168.0.70   | 8000    | Password manager        |
| Nginx Proxy Manager  | 104   | 192.168.0.65   | 81      | Reverse proxy           |
| WordPress            | 105   | 192.168.0.100  | 80      | Website                 |
| ActualBudget         | 106   | 192.168.0.60   | 5006    | Personal finance        |
| Glance               | 107   | 192.168.0.41   | 8080    | Dashboard               |
| Ghostfolio           | 108   | 192.168.0.43   | 3333    | Investment tracking     |
| Uptime Kuma          | 109   | 192.168.0.45   | 3001    | Monitoring              |
| Jellyfin             | 110   | 192.168.0.110  | 8096    | Media server            |
| Tailscale            | 1000  | 192.168.0.25   | —       | VPN mesh                |

## Networking & IP Management

- Todos os LXCs críticos usam endereçamento estático
- DNS centralizado via Pi-hole
- Gateway único no router
- Tailscale usado como overlay VPN para acesso remoto seguro
- Nenhum serviço exposto publicamente sem proxy

## Dashboard (Glance)

O Glance é utilizado como ponto central de acesso a todos os serviços internos.

- Acesso rápido
- Organização por categorias (Infra, Media, Apps)
- Configuração em YAML versionada

**Localização**: `/opt/glance/glance.yml`

## Media Stack

### Current Setup

- qBittorrent
- Jellyfin
- Media storage montado no host Proxmox

### Directory Structure

/mnt/pve/media/

├── downloads/

├── movies/

└── series/

### Planned

- VPN gateway dedicado para downloads
- Hardening de tráfego
- Automação adicional

## Security Considerations

- LXCs unprivileged
- Sem exposição direta à Internet
- Acesso remoto apenas via VPN
- HTTPS preparado mas dependente de domínio
- Separação clara entre serviços

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
