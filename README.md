# Ansible Hardening

Este repositório contém uma configuração do Ansible para realizar o hardening de sistemas Ubuntu 20.04, seguindo as diretrizes dos CIS Benchmarks. O projeto utiliza roles e collections do Ansible para configurar e fortalecer a segurança dos servidores, e inclui avaliações de segurança com OpenSCAP.

## Estrutura do Projeto

O repositório está organizado da seguinte forma:

- `/requirements.yml`: Define as collections do Ansible necessárias.
- `/group_vars/cis.yml`: Variáveis globais para a configuração de hardening.
- `/host_vars/desktop1/cis.yml`: Variáveis específicas para o host `desktop1`.
- `/host_vars/master/cis.yml`: Variáveis específicas para o host `master`.
- `/hosts/hosts.yml`: Arquivo de inventário do Ansible.
- `/roles/requirements.yml`: Define as roles necessárias para o projeto.
- `/ansible.cfg`: Configurações do Ansible.
- `/hardening.yml`: Playbook principal para aplicar o hardening.
- `/openscap_report_desktop.yml`: Playbook para executar avaliações de segurança com OpenSCAP e gerar relatórios no ambiente desktop.
- - `/openscap_report_servers.yml`: Playbook para executar avaliações de segurança com OpenSCAP e gerar relatórios em servidores.
- - `/poweroff_hosts.yml`: Playbook para desligar os hosts.
- - `/reboot_hosts.yml`: Playbook para reiniciar os hosts.
- - `/remediate_desktop.yml`:
- - `/remediate_hosts.yml`: 
- - `/remediate_master.yml`: 

## Configuração

1. **Inventário**: O arquivo `awx/hosts/hosts.yml` contém a definição dos hosts e grupos de hosts.

2. **Variáveis**: As variáveis globais estão em `awx/group_vars/cis.yml`, enquanto as variáveis específicas para cada host estão em `awx/host_vars/`, neste caso para o `master` e `desktop1`.

## Roles Utilizadas

### `cis-hardening`

O role `cis-hardening` faz parte do repositório `ansible-lockdown`, que aplica as recomendações de segurança baseadas nos benchmarks CIS para sistemas Ubuntu.

- **Repositório**: [ansible-lockdown](https://github.com/ansible-lockdown)
- **Role**: `cis-hardening`
