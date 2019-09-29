# Rede de Citações

Extração dos dados da [Scopus](https://www2.scopus.com/search/form.uri?display=basic&zone=header&origin=searchbasic) para montar uma rede de citações. 

Como a base extraída será utilizada para a estimação de parâmetros e validação de alguns modelos de simulação, foi levada em consideração a quantidade de periódicos e artigos, assim como um intervalo de tempo bem longo. 

## Passo a Passo da Extração dos Dados

1. Na base do [Web of Science](http://apps.webofknowledge.com/WOS_GeneralSearch_input.do?product=WOS&search_mode=GeneralSearch&SID=5DESZKCV7UXKP8CAy8C&preferencesSaved=), escolher uma área de pubicação e obter a listagem de periódicos. Usando o WoS, foi obtida uma listagem de todos os periódicos publicados na categoria escolhida (**MATHEMATICS**). A fim de filtrar os resultados, foi escolhida uma subárea: **LOGIC**.


2. Usando a API do Scopus, pesquisar os artigos publicados por cada um desses periódicos.


3. Usando a API do Scopus, extrair e armazenar as informações de cada artigo. As informações extraídas são armazenadas em dois diconários, um contendo as informações dos artigos (`info_articles`) e outro contendo as informações dos periódicos (`info_journals`). Essas estruturas foram pensadas para serem utilizadas no PyMongo.


4. Usando a API do Scopus, extrair e armazenar as informações das referências de cada artigo.


## Algumas das Instalações Requeridas

A coleta dos dados foi feita utilizando uma API-Wrapper baseada em Python para acessar o Scopus.

* [pybliometrics](https://github.com/pybliometrics-dev/pybliometrics/) é uma biblioteca do Python para para extrair, armazenar em cache e extrair dados do banco de dados Scopus. A documentação encontra-se [aqui](https://pybliometrics.readthedocs.io/en/stable/). Para a geração das chaves para API: [Elsevier Developers](https://dev.elsevier.com/apikey/manage);
* [mongoDB](https://www.mongodb.com);
* [PyMongo](https://api.mongodb.com/python/current/);
* [Pandas](https://pandas.pydata.org);
* [csv](https://docs.python.org/3/library/csv.html);
* [pickle](https://docs.python.org/3/library/pickle.html#module-pickle);
* [Selenium](http://www.seleniumhq.org);
* [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/);
* [time](https://docs.python.org/3/library/time.html);
* [os](https://docs.python.org/3/library/os.html);
* [itertools](https://docs.python.org/3/library/itertools.html);
* [gc](https://docs.python.org/3/library/gc.html);
* [tqdm](https://tqdm.github.io);
* [configparser](https://docs.python.org/3/library/configparser.html);
* [getpass](https://docs.python.org/3.6/library/getpass.html) - para o caso de precisar um login.

Para utilizar o Selenium, é necessário de uma API [WebDriver](http://www.seleniumhq.org/projects/webdriver/), como por exemplo, o [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/downloads) (uma implementação que controla um navegador Chrome executado na máquina local).

## Informações dos Dados Extraídos

