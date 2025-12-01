# 🎹 Partitura 3D Sonora: Protótipo de Partitura Musical Interativa

## ✨ Visão Geral do Projeto

O **Partitura 3D Sonora** é um sistema físico-eletrônico desenvolvido para superar os desafios históricos no ensino de teoria musical para pessoas cegas ou com baixa visão. O projeto integra **tecnologia assistiva**, **manufatura aditiva** e **dispositivos eletrônicos interativos** para promover acessibilidade, autonomia e inclusão no aprendizado musical.

O dispositivo traduz a lógica da partitura visual para o domínio do **tato**, permitindo que o usuário manipule e escute a música de forma multissensorial.

### Autoria

| Função | Nome |
| :--- | :--- |
| **Autores** | Ana Julia Turko dos Santos, Jesús Alberto López Oviedo |
| **Orientador** | Marcos Eduardo Pivaro Monteiro |

---

## ⚙️ Arquitetura e Funcionamento

O sistema é composto por uma base modular impressa em 3D e peças móveis interativas, tudo controlado por um microcontrolador ESP-32.

### 1. Componentes Físicos (Hardware)

* **Base Modular:** Estrutura impressa em 3D que reproduz a pauta musical tradicional (Clave de Sol, compasso $4/4$).
* **Matriz de Teclas (Keyboard Matrix):** A base funciona como uma matriz onde cada posição possui contatos e um diodo para evitar *ghosting*.
* **Peças Musicais:** Peças móveis que representam figuras e pausas musicais (desde semibreve até semicolcheia).

### 2. Identificação Eletrônica

O sistema utiliza um método de identificação por resistência e posição:

* **Assinatura Eletrônica:** Cada peça musical contém um **resistor** específico que funciona como uma assinatura eletrônica.
* **Leitura Robusta:** Após a mudança de *design*, os resistores utilizados são **THT de 1/8 W**, soldados em um conector *header* fêmea para garantir um acoplamento mais seguro e robusto com a base.
* **Processamento:** Quando uma peça é encaixada, o sistema detecta simultaneamente a **posição física** (linha ou espaço) e o **valor resistivo** da peça.

### 3. Processamento e Saída Sonora

O microcontrolador ESP-32 processa os dados da seguinte forma:

1.  **Interpretação:** Combina a posição (linha/espaço) e o valor resistivo para determinar a presença ou ausência de som (nota ou pausa).
2.  **Parâmetros Musicais:** Define a **altura musical (pitch)** e a **duração** do som ou pausa.
3.  **Reprodução:** Após a interpretação, o sistema reproduz o som correspondente, proporcionando uma experiência sensorial completa.

---

## 🏗️ Status e Próximas Etapas de Desenvolvimento

### 🟢 Progresso Atual

* Definição de 10 faixas de resistência para cada figura e pausa musical para leituras analógicas estáveis.
* Substituição dos resistores SMD pelo modelo **THT de 1/8 W** e padronização do encaixe com conectores *header* fêmea para solucionar problemas de aderência e precisão.
* Modelagem 3D das peças musicais e do pino de encaixe, estabelecendo a base mecânica e eletrônica para a integração completa.

### 🚀 Próximas Etapas

1.  **Validação da Matriz Reduzida:** Implementação do sistema de identificação eletrônica em uma **matriz de testes 2x2** utilizando o ESP-32, validando o reconhecimento das peças e a reprodução sonora em pequena escala.
2.  **Expansão Progressiva:** Aumentar gradualmente a matriz de testes até atingir a **matriz completa (9 linhas x 7 colunas)**, para garantir a estabilidade das leituras e o tempo de resposta.
3.  **Protótipo Físico do Circuito:** Construção da primeira versão do circuito em **placa perfurada** para validar o roteamento básico e testar a robustez das conexões elétricas.
4.  **Projeto da PCB:** Projeção da **Placa de Circuito Impresso (PCB)** final, organizando componentes, trilhas e interfaces.
5.  **Suporte Estrutural Final:** Projeto do suporte que integrará a PCB, conectores e a Partitura 3D, visando ergonomia e segurança para o usuário final.

---

## 📦 Estrutura do Repositório

| Diretório | Conteúdo |
| :--- | :--- |
| **`hardware/modelagem_3d/`** | Arquivos STL/CAD para a Base Modular e as Peças Musicais. |
| **`hardware/esquemas_eletricos/`** | Diagramas de circuito (matriz de teclas) e projeto da PCB. |
| **`software/firmware_esp32/`** | Código (Arduino/C++) para o microcontrolador ESP-32, responsável pela leitura ADC, interpretação da matriz e reprodução sonora. |
| **`documentacao/`** | Relatórios de progresso, tabelas de valores ADC/resistência e artigos técnicos. |

---

## 🛠️ Tecnologias Principais

* **Microcontrolador:** ESP-32
* **Manufatura:** Impressão 3D
* **Componentes:** Resistores THT (1/8 W), Conectores *Header*, Diodos.
* **Princípios:** Tecnologia Assistiva, Cognição Multissensorial, Engenharia Aplicada.

---

## 🤝 Como Contribuir

A comunidade é fundamental para o sucesso de um projeto inclusivo! Aceitamos contribuições nas seguintes áreas:

* **Eletrônica/Firmware:** Otimização do código para o escaneamento da matriz e melhoria do sistema de reprodução sonora do ESP-32.
* **Design Mecânico:** Melhorias na ergonomia e na robustez das peças 3D.
* **Design Musical:** Sugestões para expansão do repertório de figuras, claves ou compassos.

Por favor, leia o arquivo **`CONTRIBUTING.md`** para detalhes sobre o fluxo de trabalho de contribuição.

---

## 📜 Licença

[**LICENÇA A SER INSERIDA AQUI**]
*(Sugestão: Uma licença de código aberto como MIT ou GPL, e uma licença Creative Commons para os arquivos de hardware.)*
