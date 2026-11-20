# Slackware 15.0 — perfis core minimalistas

Este repositório reúne dois conjuntos de tagfiles para instalar o Slackware 15.0 em modo texto, com uma seleção enxuta voltada a rede, compilação e suporte a hardware. Os perfis não incluem um ambiente gráfico completo e devem ser usados com a mídia oficial da mesma versão e arquitetura.

## Arquivos para download

Os links abaixo apontam diretamente para os arquivos ZIP publicados na branch `main`:

| Arquivo | Arquitetura | Inicialização |
|---|---|---|
| [slackware-15.0-x86-tagfiles.zip — download](https://github.com/garme/tagfiles/raw/refs/heads/main/slackware-15.0-x86-tagfiles.zip) | x86 (32 bits) | BIOS/Legacy |
| [slackware64-15.0-x86_64-tagfiles.zip — download](https://github.com/garme/tagfiles/raw/refs/heads/main/slackware64-15.0-x86_64-tagfiles.zip) | x86_64 (64 bits) | BIOS ou UEFI |

Os perfis selecionam **185 pacotes para x86** e **183 para x86_64**. Os tagfiles são aplicados pelo instalador do Slackware usando a opção **tagpath**.

## Principais pacotes

- **A — sistema base:** ferramentas essenciais, kernels, firmware, utilitários de disco e carregadores de inicialização. Inclui `smartmontools`; o perfil x86_64 também inclui suporte UEFI (`efibootmgr`, `efivar` e `elilo`).
- **AP — aplicativos e administração:** `slackpkg`, `sudo`, `vim`, `nano`, `neofetch`, manuais e utilitários. Também inclui `dmidecode`, `lm_sensors` e `alsa-utils`.
- **D — desenvolvimento:** GCC, binutils, make, Autotools, CMake, Meson, Ninja, Git, Python 3 e Perl.
- **L — bibliotecas:** glibc, bibliotecas de desenvolvimento e suporte, incluindo `libsodium`, `libseccomp` e `alsa-lib`.
- **N — rede:** NetworkManager, DHCP, OpenSSH, curl, wget, rsync, tcpdump, ferramentas Wi-Fi e NTP.
- **X — bibliotecas de entrada:** `libinput`, `libevdev`, `mtdev` e `libwacom`, bibliotecas de entrada relacionadas ao X. A seleção não instala um ambiente gráfico completo.

Os perfis também incluem `lynx`, `xfsprogs`, `pciutils` e `usbutils`, entre outros utilitários necessários ao uso básico e à compilação de software.

## Diferenças entre x86 e x86_64

- **x86 (32 bits):** inclui kernels e módulos SMP e sem SMP. O perfil foi montado para BIOS/Legacy; também inclui `efibootmgr` e `efivar` para consulta e administração de variáveis UEFI quando aplicável.
- **x86_64 (64 bits):** usa os kernels próprios de 64 bits, sem variantes SMP, e inclui `efibootmgr`, `efivar` e `elilo` para suporte UEFI. Também mantém opções de inicialização BIOS, como GRUB e LILO.

O perfil x86_64 não configura multilib. Aplicações de 32 bits exigem configuração adicional.

## Instalação

1. Extraia o ZIP correspondente à arquitetura e copie a pasta `tagfiles` para um segundo pendrive, preservando sua estrutura de diretórios.
2. Inicie o computador pela mídia oficial correspondente do Slackware 15.0 e execute `setup` como `root`.
3. Na seleção de séries, marque **A, AP, D, L, N e X**. A série X é necessária para instalar as bibliotecas de entrada selecionadas; as demais entradas dessa série continuam marcadas para pular conforme o tagfile.
4. Escolha o modo **tagpath** e informe o caminho da pasta `tagfiles` no segundo pendrive.
5. Conclua a instalação e configure o carregador de inicialização conforme o firmware do computador.

