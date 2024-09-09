---
title: Como Manter o X Bloqueado Nos Seus Dispositivos
date: 2024-09-07 14:33:00 -0300
categories: [Network, Security, Social Media]
tags: [Network, Security, X]
author: thiagobmi
---

Recentemente, o X (antigo Twitter) foi foco de diversas controvérsias que resultaram no bloqueio da plataforma para usuários brasileiros. A decisão foi tomada pelo ministro do Supremo Tribunal Federal (STF), Alexandre de Moraes, que afirmou que a rede social descumpriu ordens judiciais de remover perfis e conteúdos considerados criminosos. A situação se agravou após Elon Musk, atual proprietário do X, ordenar o fechamento do escritório da empresa no Brasil.

Desconsiderando os fatores políticos e sociais que desencadearam esse acontecimento, ficar alguns dias sem acesso ao X se tornou em uma ótima experiência. Além de consumir menos conteúdos tóxicos e inúteis, pude focar em atividades mais saudáveis e produtivas.

No momento, ainda não é possível prever quanto tempo durará o bloqueio, que pode se estender por dias ou até anos, dependendo das decisões de Musk e Moraes. Por isso, decidi bloquear o X em todos os meus dispositivos e fazer um tutorial ensinando quem quiser fazer o mesmo.


## 1. Bloqueando o X no Windows
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

## 2. Bloqueando o X no Linux
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

## 3. Bloqueando o X no macOS
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

## 4. Bloqueando o X em um Roteador
Bloquear um site diretamente no roteador é uma maneira eficaz de impedir que qualquer dispositivo conectado à rede acesse o X. No entanto, o processo pode variar dependendo do modelo e fabricante do roteador. Abaixo, encontra-se um guia geral para bloquear sites em um roteador.

### Passo a passo:
1. Acesse a interface do roteador inserindo o IP (geralmente `192.168.0.1` ou `192.168.1.1`) no navegador.
2. Faça login com suas credenciais de administrador.
3. Navegue até a seção de **Firewall** ou **Controle de Acesso**.
4. Procure por uma opção de **Bloqueio de Sites** ou **Filtro de URLs**.
5. Adicione `x.com` e `twitter.com` à lista de sites bloqueados.
6. Salve as alterações e reinicie o roteador se necessário.

Com essas instruções, você poderá bloquear o X (antigo Twitter) em qualquer um dos sistemas operacionais ou na sua rede local através do roteador.

## Como Esse Método Funciona?

### 1. O que é o Arquivo **hosts**?
- O arquivo **hosts** é um arquivo de sistema usado para mapear nomes de domínio para endereços IP localmente.
- Ele funciona de forma similar a um DNS, mas é consultado localmente no dispositivo.

### 2. Como o Bloqueio Funciona?
- Quando você adiciona uma entrada como `127.0.0.1 x.com` no arquivo **hosts**, o sistema redireciona todas as solicitações para esse domínio ao IP **127.0.0.1** (localhost).
- O **localhost** se refere ao próprio dispositivo. Como não há servidor rodando localmente para responder, a solicitação falha.

#### Resultado:
- Tentativas de acessar o site resultam em erro, como "Página não encontrada" ou "Conexão recusada", pois o navegador tenta acessar o próprio dispositivo sem sucesso.

### 3. Prioridade do Arquivo **hosts** sobre DNS:
- O arquivo **hosts** tem prioridade sobre o DNS.
- Se um domínio estiver no arquivo **hosts**, o sistema o redireciona localmente antes de consultar qualquer servidor DNS na internet.
