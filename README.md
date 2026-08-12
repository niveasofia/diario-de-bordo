## Encontro nº I — [11/08/2026] 
**Curso:** Engenharia de Software
---
**Integrantes:**
- Nivea Sofia de Cas
- Yasmin Fernanda de Carvalho

**Pauta:** Estudo sobre segurança do banco de dados

<div style="text-align: justify;">
<b>Desenvolvimento:</b> Durante o encontro, foram discutidos os principais conceitos sobre segurança do banco de dados, organizados a seguir:
</div>

## O que é?

<div style="text-align: justify;">
&nbsp;&nbsp; Um conjunto de ferramentas e medidas que busca garantir a <b>confidencialidade, integridade e disponibilidade dos dados</b>, por meio de restringir as funcionalidades e o acesso ao banco de dados de forma criteriosa e controlada.
</div>

## Qual a importância?

<div style="text-align: justify;">
&nbsp;&nbsp; Muitos podem ser os danos causados ao ocorrer um vazamento de dados. Dentre eles, podemos citar projetos secretos ainda em desenvolvimento, que outras pessoas podem fazer uso indevido, fazendo com que aquilo que seria um lançamento extraordinário perca seu impacto. <br>
&nbsp;&nbsp; É importante levar em consideração que um vazamento de dados confidenciais tem um custo real, que pode ser altíssimo, além da necessidade de a empresa arcar com custos para investigar as causas. Uma empresa pode ficar marcada pelo ocorrido e perder sua credibilidade no mercado.
</div>

## Quais são os pilares da segurança?

<div style="text-align: justify;">
&nbsp;&nbsp; Podemos defini-los como a Tríade CID: <br>
&nbsp;&nbsp;<b>Confidencialidade</b> - uso da criptografia, de modo que mesmo que uma informação seja “roubada” em trânsito ou mesmo armazenada no banco de dados, não seja possível lê-la. Aplica-se também o princípio do menor privilégio, tendo acesso apenas ao que é estritamente necessário, além da rastreabilidade de acessos: quem acessou e o que acessou.<br>
&nbsp;&nbsp; <b>Integridade</b> - garantia de que a informação que entra no banco de dados é a informação correta, e de que ela não será alterada por uma falha no sistema ou por um usuário não autorizado. Caso haja alteração, deve haver a rastreabilidade para identificar quem a fez.<br>
&nbsp;&nbsp; <b>Disponibilidade</b> - garantia de acesso à informação que está no banco de dados. Ela não pode ficar indisponível, mesmo diante de uma queda no sistema ou ataque ao servidor, por isso o uso de backups, tanto físicos quanto em nuvem. A segurança deve garantir detecção rápida de tentativas de ataque, que possam sobrecarregar o servidor, para que seja possível mitigar os danos.
</div>

## Principais ameaças à segurança do banco de dados

| Ameaça | O que é |
|---|---|
| **Vulnerabilidades de software** | Falhas em softwares de gerenciamento exploradas por hackers — manter sistemas sempre atualizados |
| **Injeção SQL/NoSQL** | Comandos maliciosos inseridos em aplicações para acessar ou alterar dados |
| **Estouro de buffer** | Um programa tenta armazenar mais dados do que a memória permite |
| **Malware** | Programas maliciosos que exploram vulnerabilidades e causam danos |
| **Ataques a backups** | Cópias de segurança também precisam ser protegidas |
| **Ataques DoS** | Sobrecarregam o servidor, impedindo o acesso de usuários legítimos |

> O aumento da quantidade de dados, a expansão das infraestruturas de tecnologia e as exigências de segurança tornam a proteção dos bancos de dados cada vez mais importante.

---

## Principais medidas de segurança do banco de dados

A segurança do banco de dados deve proteger não apenas o banco em si, mas também a rede, os servidores, as aplicações e os dispositivos que possuem acesso a ele.

- **Segurança física** — manter os servidores em locais seguros e adequados.
- **Controle de acesso** — permitir que somente usuários autorizados tenham acesso e limitar suas permissões ao necessário.
- **Segurança de usuários e dispositivos** — monitorar quem acessa os dados e proteger os dispositivos utilizados.
- **Criptografia** — proteger os dados armazenados e durante a transmissão, incluindo informações de acesso.
- **Segurança do software** — manter o sistema de gerenciamento do banco atualizado e instalar os patches de segurança.
- **Segurança de aplicações e servidores** — proteger e testar aplicações que se conectam ao banco de dados.
- **Segurança dos backups** — proteger cópias de segurança com o mesmo nível de proteção do banco original.
- **Auditoria** — registrar acessos e operações realizadas com dados importantes, além de realizar verificações de segurança regularmente.

---

## O que é criptografia?

<div style="text-align: justify;">
&nbsp;&nbsp; Uma forma de transformar um texto ou uma informação legível em algo ilegível. É embaralhar as informações contidas, se caracterizando pelo processo de cifragem, de forma que apenas quem possui uma chave de acesso, consiga desembaralhá-las para entender.<br>
&nbsp;&nbsp; A chave possui duas formas de uso:<br>
</div>

- **Simétrica:** uma mesma chave para as duas partes.
- **Assimétrica:** duas chaves diferentes, sendo uma chave pública para criptografar as informações e uma chave privada correspondente, para descriptografar.

## Como o controle de acessos afeta a modelagem?

<div style="text-align: justify;">
&nbsp;&nbsp;Afeta ao definir a estrutura dos dados (tabelas, colunas e relacionamentos), que devem suportar e aplicar políticas de segurança. É importante também impedir e monitorar tentativas de acesso de quem não possui autorização para acessar determinado conteúdo, e ao mesmo tempo facilitar o acesso de quem precisa dessa informação.<br>
&nbsp;&nbsp;É necessário definir, na modelagem, como será feita a relação entre sujeitos e objetos, onde será definido se um sujeito pode acessar um objeto, e o que ele pode fazer com esse objeto, delimitando as ações permitidas, podendo ser como exemplo apenas leitura, ou ler e alterar.<br>
&nbsp;&nbsp;Os impactos estão na aplicação do princípio de menor privilégio, tratando nível de sensibilidade das informações e definindo dados que apenas o próprio cliente final possui acesso, como suas senhas. Há impacto também no uso da rastreabilidade e nos logs de auditoria, permitindo detectar quem alterou determinada informação e em qual data.<br>
&nbsp;&nbsp;Dessa forma, os sistemas de controle de acesso, garantem que apenas sujeitos autenticados e autorizados tenham acesso a informações previamente aprovadas, conectando as regras de negócio à estrutura física e lógica do banco. 
</div>

## Diagrama: Modelo Entidade-Relacionamento (Sistema de Biblioteca)

![Diagrama Entidade-Relacionamento do sistema de biblioteca](biblioteca.jpg)

**Resumo:** O diagrama modela um sistema de biblioteca com três entidades: **Usuário** (CPF, Nome, Contato, Endereço), **Movimentação** (IdMovimentação, Data, Tipo — que indica se é Empréstimo ou Devolução) e **Livros** (IdLivro, Nome, Autor, Gênero, QuantEstoque).

A entidade Usuário se conecta à entidade Movimentação através do relacionamento **Realiza**. A cardinalidade (1, n) do lado de Usuário indica que um usuário pode realizar uma ou várias movimentações. A cardinalidade (1, 1) do lado de Movimentação indica que cada movimentação é realizada por exatamente um único usuário.

A entidade Movimentação se conecta à entidade Livros através do relacionamento **Contém**. A cardinalidade (1, n) do lado de Movimentação indica que cada movimentação pode conter um ou vários livros. A cardinalidade (1, 1) do lado de Livros indica que cada livro está associado a exatamente uma movimentação.

Em conjunto, o modelo representa o fluxo de empréstimos e devoluções de uma biblioteca: um usuário realiza movimentações (empréstimos ou devoluções), e cada movimentação registra os livros envolvidos nessa operação.

<p align="center"><sub>Resumo de estudo — Segurança de Banco de Dados</sub></p>