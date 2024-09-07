---
title: Como Bloquear o X Nos Seus Dispositivos
date: 2024-09-07 14:33:00 -0300
categories: [Network, Security]
tags: [Network, Security, X]
author: thiagobmi
---

## Como Bloquear o X Nos Seus Dispositivos

Recentemente, o X (antigo Twitter) foi foco de diversas controvérsias que resultaram no bloqueio da plataforma para usuários brasileiros. A decisão foi tomada pelo ministro do Supremo Tribunal Federal (STF), Alexandre de Moraes, que afirmou que a rede social descumpriu ordens judiciais de remover conteúdos considerados ofensivos e ameaçadores. A situação se agravou após Elon Musk, atual proprietário do X, ordenar o fechamento do escritório da empresa no Brasil.

Desconsiderando os fatores políticos e sociais que desencadearam esse acontecimento, ficar alguns dias sem acesso ao X se tornou em uma ótima experiência. Além de consumir menos conteúdos tóxicos e inúteis, pude focar em atividades mais saudáveis e produtivas. Por isso, decidi bloquear o X em todos os meus dispositivos. Neste post, vou mostrar como fiz isso e como você pode fazer o mesmo.


## 1. Bloquear X no Windows
### Passo a passo:
1. Abra o **Bloco de Notas** como administrador.
2. Navegue até o arquivo `hosts` no caminho: `C:\Windows\System32\drivers\etc\hosts`.
3. Adicione as seguintes linhas no final do arquivo:
   ```
   127.0.0.1 x.com
   127.0.0.1 twitter.com
   ```
4. Salve o arquivo.
5. Reinicie o navegador para aplicar as alterações.

## 2. Bloquear X no Linux
### Passo a passo:
1. Abra um terminal.
2. Use o comando abaixo para abrir o arquivo `hosts` com privilégios de superusuário:
   ```bash
   sudo nano /etc/hosts
   ```
3. No final do arquivo, adicione as seguintes linhas:
   ```
   127.0.0.1 x.com
   127.0.0.1 twitter.com
   ```
4. Salve o arquivo pressionando `CTRL + O`, depois saia pressionando `CTRL + X`.
5. Reinicie o navegador para aplicar as alterações.

## 3. Bloquear X no macOS
### Passo a passo:
1. Abra o **Terminal**.
2. Use o comando abaixo para abrir o arquivo `hosts`:
   ```bash
   sudo nano /etc/hosts
   ```
3. No final do arquivo, adicione as seguintes linhas:
   ```
   127.0.0.1 x.com
   127.0.0.1 twitter.com
   ```
4. Salve o arquivo pressionando `CTRL + O` e depois saia com `CTRL + X`.
5. Limpe o cache do DNS usando o comando:
   ```bash
   sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder
   ```
6. Reinicie o navegador.

## 4. Bloquear X em um Roteador
Bloquear um site diretamente no roteador é uma maneira eficaz de impedir que qualquer dispositivo conectado à rede acesse o X. Esse pode ser um ótimo método para tornar sua casa um ambienta mais tranquilo e com menos discussões desnecessárias.

### Passo a passo:
1. Acesse a interface do roteador inserindo o IP (geralmente `192.168.0.1` ou `192.168.1.1`) no navegador.
2. Faça login com suas credenciais de administrador.
3. Navegue até a seção de **Firewall** ou **Controle de Acesso**.
4. Procure por uma opção de **Bloqueio de Sites** ou **Filtro de URLs**.
5. Adicione `x.com` e `twitter.com` à lista de sites bloqueados.
6. Salve as alterações e reinicie o roteador se necessário.

Com essas instruções, você poderá bloquear o X (antigo Twitter) em qualquer um dos sistemas operacionais ou na sua rede local através do roteador.
