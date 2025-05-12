````markdown
# 🔄 OnSync: VATCAIXA_update_onSync.js
Este dataset foi desenvolvido com o objetivo de manter a integridade dos dados no ambiente Fluig, realizando verificações periódicas em tabelas específicas do banco de dados e corrigindo inconsistências automaticamente.
````
![image](https://github.com/user-attachments/assets/7fc8f2f1-341e-495b-b00d-2893bbf9f0dc)
````
---

## 🎯 Objetivo

Realizar **verificações agendadas** no banco de dados e **corrigir informações inconsistentes** com base em regras pré-definidas, garantindo que os dados reflitam o estado correto da operação do negócio.

---

## ⚙️ Funcionamento

- Executado automaticamente em intervalos regulares (via cron ou evento programado no Fluig)
- Realiza um **SELECT** em tabelas-chave para detectar divergências ou dados não sincronizados
- Quando detecta inconsistências, aplica **UPDATE** nos registros necessários
- Finaliza o processo com um COMMIT garantindo a persistência das correções e envia um email para as partes interessadas informando a correção.
````
![image](https://github.com/user-attachments/assets/f2c24eae-4e2b-409a-8842-e5bb103e516a)
````
---

## 📌 Casos de Uso

- Corrigir registros duplicados ou mal sincronizados na tabela `VATCAIXA`
- Garantir que campos essenciais estejam sempre atualizados com os valores esperados
- Evitar falhas em relatórios ou integrações causadas por dados obsoletos

---

## 💡 Tecnologias Utilizadas

- TOTVS Fluig Dataset Customizado (JavaScript)
- JDBC Connection com banco de dados Oracle/PostgreSQL
- SQL para validação e correção de dados

---

## 📝 Exemplo de Log (simulação)
```txt
[INFO] Iniciando verificação na tabela VATCAIXA
[INFO] Encontrados 3 registros com inconsistência
[UPDATE] Registro ID 105 atualizado com sucesso
[UPDATE] Registro ID 112 atualizado com sucesso
[UPDATE] Registro ID 128 atualizado com sucesso
[COMMIT] Alterações salvas com sucesso
[INFO] Execução finalizada em 1.2 segundos
````

---

## ⚠️ Observações
* Este dataset foi projetado para rodar em ambiente controlado. Recomenda-se testes em homologação antes da aplicação em produção.
* As instruções SQL e os critérios de verificação podem ser adaptados conforme o cenário e estrutura de dados de cada cliente.

---

## 👨‍💻 Autor
Desenvolvido por [Raphael Bezerra](https://github.com/devraphaelbezerra)
Especialista em automação de processos e integrações no ecossistema TOTVS Fluig.

```
Raphael Bezerra
```

