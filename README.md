# Slackware 15.0 — perfis core minimalistas

Este repositório reúne dois conjuntos de tagfiles para instalar um sistema Slackware 15.0 em modo texto, com uma seleção enxuta de pacotes voltada a rede e compilação. Os perfis não incluem ambiente gráfico e devem ser usados com a mídia oficial da mesma versão e arquitetura.

## Arquivos

| Arquivo | Arquitetura | Inicialização |
|---|---|---|
| [slackware-15.0-x86-tagfiles (32 bits)](./slackware-15.0-x86-tagfiles%281%29.zip) | x86 | BIOS/Legacy |
| [slackware64-15.0-x86_64-tagfiles (64 bits)](./slackware64-15.0-x86_64-tagfiles%281%29.zip) | x86_64 | BIOS ou UEFI |

Cada perfil seleciona 174 pacotes nas séries **A, AP, D, L e N**. Os tagfiles são aplicados pelo instalador do Slackware usando a opção **tagpath**.

## Principais pacotes

- **A — sistema base:** ferramentas essenciais do sistema, kernels, firmware, utilitários de disco e carregadores de inicialização.
- **AP — aplicativos e administração:** slackpkg, sudo, vim, nano, neofetch, manuais e utilitários.
- **D — desenvolvimento:** GCC, binutils, make, Autotools, CMake, Meson, Ninja, Git, Python 3 e Perl.
- **L — bibliotecas:** glibc, bibliotecas de desenvolvimento e suporte, incluindo libsodium e libseccomp.
- **N — rede:** NetworkManager, DHCP, OpenSSH, curl, wget, rsync, tcpdump, ferramentas Wi-Fi e ntp.

Os perfis também incluem lynx, xfsprogs e outros utilitários necessários ao uso básico e à compilação de software.

## Diferenças entre x86 e x86_64

A seleção é quase igual nas duas arquiteturas. A diferença principal está nos pacotes de kernel e de inicialização:

- **x86 (32 bits):** inclui kernels e módulos SMP e sem SMP. O perfil está preparado para BIOS/Legacy.
- **x86_64 (64 bits):** usa os kernels próprios de 64 bits, sem variantes SMP, e inclui efibootmgr, efivar e elilo para suporte a UEFI. Também mantém opções de inicialização BIOS, como GRUB e LILO.

O perfil x86_64 não configura multilib. Aplicações de 32 bits exigem configuração adicional.

## Uso

Extraia o ZIP correspondente, copie a pasta tagfiles para um pendrive e, durante a instalação feita pela mídia oficial correspondente, selecione as séries **A, AP, D, L e N**. Escolha **tagpath** e indique o diretório tagfiles copiado para o pendrive.
