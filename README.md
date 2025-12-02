# 🏥 Clínica Vida+ – Sistema de Gestão de Pacientes

Sistema completo de gestão de pacientes desenvolvido em Python, com menu em console e interface gráfica (GUI) usando `tkinter`. O projeto está organizado em pacotes, separando lógica de negócio, configuração, interface gráfica e dados de apoio.

## 📂 Estrutura do Projeto

PROJETO-ANHANGUERA/
├── sistema_clinica_vida_plus_completo.py # MAIN (menu console + integração GUI)

├── config_dados/ # Configurações e regras de negócio

│ ├── init.py

│ ├── config.py # Constantes, usuários, caminhos de backup

│ ├── utils.py # Validações, helpers e funções de console


│ ├── modelos.py # Classes Paciente, Clínica etc.

│ ├── persistencia.py # Backup, restauração e serialização JSON

│ ├── controle_acesso.py # Lógica booleana de controle de acesso

│ └── fila_atendimento.py # Fila FIFO com validação

├── interface/

│ ├── init.py
│ └── interface_gui_melhorada.py # Interface gráfica corrigida (4 abas)

├── arquivos csv/

│ ├── tabela_verdade_consulta_normal.csv # Tabelas verdade usadas no projeto

│ └── tabela_verdade_emergencia.csv

└── backup_pacientes.json # Exemplo de arquivo de backup

## ✨ Funcionalidades

- Autenticação:
  - Login obrigatório (usuários definidos em `config_dados/config.py`).
  - Limite de tentativas e mensagens amigáveis no console.

- Gestão de Pacientes (console e GUI):
  - Cadastro, listagem, busca, edição e remoção.
  - Estatísticas (total, idade média, mínima e máxima).
  - Validações de nome, idade e telefone via `config_dados/utils.py`.

- Controle de Acesso (Passo 3):
  - Lógica booleana A, B, C, D para autorizar atendimentos.
  - Cenários de consulta normal e emergência.
  - Interface em console e na aba de controle de acesso da GUI.

- Fila de Atendimento (Passo 4):
  - Estrutura FIFO completa.
  - Somente pacientes cadastrados entram na fila.
  - Impede duplicidade e limita a 3 pacientes simultâneos.
  - Histórico de atendidos.
  - Integração com GUI por meio de ComboBox e painel visual.

- Interface Gráfica (GUI melhorada):
  - 4 abas:
    - Gestão de Pacientes.
    - Controle de Acesso.
    - Fila de Atendimento.
    - Ferramentas (backup, restauração, informações do sistema).
  - Tratamento de erros com `try/except` em pontos críticos.
  - Design com `ttk.Notebook`, `Treeview`, labels e botões estilizados.

- Persistência e Backup:
  - Salvamento em JSON (`backup_pacientes.json` ou arquivo definido em `ARQUIVO_BACKUP`).
  - Funções para fazer backup, listar backups e restaurar dados.
  - Serialização/deserialização de objetos Paciente/Clínica.

## 🛠 Tecnologias Utilizadas

- Python 3.x
- `tkinter` / `ttk` (GUI)
- JSON para armazenamento de dados
- Programação Orientada a Objetos
