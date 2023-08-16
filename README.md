# Estágio de Férias Insper 2023:
* Aluno: Pedro De Lucca S C Ferro
* Área: Gestão de Pesquisa
## Descrição:
Por meio desse README pretendo mostrar como consegui fazer o scraping de dados do Linkedin, assim como a automação de algumas tarefas na plataforma do Insper e na plataforma Lattes para buscar informações dos docentes.
## Automação Linkedin:
Para a automação do Linkedin, utilizei uma ferramenta disponível gratuitamente (Trial de 14 dias) chamada [PhantomBuster](https://phantombuster.com/). Essa ferramenta permite que você crie robôs que executam tarefas repetitivas no Linkedin, como por exemplo, acessar o perfil de um usuário e extrair informações como nome, cargo, empresa, etc. Leia a [documentação](https://phantombuster.com/automations/linkedin/3112/linkedin-profile-scraper/tutorial) disponível no site para saber a melhor maneira de se extrair os dados. 

<font color="red">ATENÇÃO:</font> é fortemente recomendado que você crie contas (Linkedin) específicas para o scraping, uma vez que há grande probabilidade de banimento. Para tentar minimizar essas chances, recomendo utilizar o navegador [Firefox](https://www.mozilla.org/pt-BR/firefox/new/) e realizar o scraping de maneira fracionada. Por exemplo, se precisa de 100 perfis rode o programa 5 vezes utilizando 20 perfis por vez. Com isso, não fica "na cara" que é um bot executando a ação.
## Automação Plataforma Insper:
Toda a automação feita dentro da [Plataforma Insper](https://cgi.insper.edu.br/PortfolioDocente/) para docentes foi realizada utilizando a linguagem de programação [Python](https://www.python.org/). Para isso, utilizaremos as seguintes bibliotecas:
* [Selenium](https://selenium-python.readthedocs.io/): biblioteca utilizada para automatizar ações em navegadores web.
```bash
pip install selenium
pip install webdriver-manager
```
* [Pandas](https://pandas.pydata.org/): biblioteca utilizada para manipulação de dados.
```bash
pip install pandas
```
<font color="red">IMPORTANTE:</font> Você precisará de um login e senha para ter acesso a platforma. Caso não tenha, entre em contato com o Help Desk do Insper.  
Para entender como o script funciona acesse o arquivo **Insper_Auto.ipynb** e siga os comentários feitos no código.

## Automação Plataforma Lattes:
Essa automação utiliza as mesmas bibliotecas do script anterior. Para entender como o script funciona acesse os arquivos e siga os comentários feitos no código.
### Script NaN:
Essa automação (**Lattes_Auto_Nan.ipynb**) foi feita visando a otimização no momento de adicionar Links para o currículo Lattes dos usuários. Para isso, o script realiza a busca do nome do docente na plataforma e, caso não encontre, completa a base de dados com "NaN". Com isso, é possível saber quais docentes não possuem o link para o currículo Lattes na base de dados. Com isso, esse script só será útil se **não tivermos o link para o currículo Lattes** dos docentes na base de dados. Caso contrário, não há necessidade de rodar esse script.
### Script semi autônomo para adicionar links Lattes:
Essa automação (**Lattes_Auto_Add.ipynb**) foi feita visando a otimização no momento de buscar currículos Lattes dos usuários. É importante ressaltar que esse script não é totalmente autônomo, uma vez que ao buscar currículos por meio do nome, a plataforma pode retornar mais de um resultado (Usuários Homônimos). Com isso, é necessário escolher o resultado correto de maneira manual.

Além disso, esse script não possui uma função específica igual aos outros presentes nesse repositório, já que para funcionar de maneira correta ele precisa estar em "loop" e, para isso, é necessário rodar numa mesma célula dentro de um arquivo jupyter.