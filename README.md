# Atividade Oscar Banco de Dados

Muito bem, Pessoal... 

Hoje vamos trabalhar com o Oscar.
A ideia de premiar ou ser premiado é para reconhecer:
- Reconhecer uma qualidade
- Reconhecer um atributo
- Reconhecer o esforço... 

Reconhecer sempre.

Nem todos os prêmios são merecidos e nem todos que merecem ganham prêmios. 
Então vale mesmo a pena, premiar? 

*Quantas vezes Natalie Portman foi indicada ao Oscar?* 

**R: Natalie Portman foi indicada ao Oscar três vezes**

<code> select count(*) from movies where name = "Natalie Portman"; </code>


*Quantos Oscars Natalie Portman ganhou?*

**R: Natalie Portman ganhou o Oscar uma vez**

<code> select count(*) from movies where name = "Natalie Portman" and  winner = "true"; </code>

*Amy Adams já ganhou algum Oscar?*

**R: Amy Adams não ganhou o Oscar**

<code> select * from movies where name = "Amy Adams" and winner= "winner"; </code>

*Toy Story 3 ganhou um Oscar em quais anos?*

**R: Toy Story 3 ganhou um Oscar em 2011**

<code>select  year_ceremony from movies where film = "Toy Story 3" and winner= "true";</code>

*Quem tem mais Oscars: a categoria "Melhor Ator" ou "Melhor Filme"?*

**R: A catergoria "Melhor Filme" tem mais Oscars**
 
 <code> select count(*) from movies where category= "BEST PICTURE" and winner="true";
 select count(*) from movies where category= "Actor" and winner="true"; </code>

*O primeiro Oscar para melhor Atriz foi para quem? Em que ano?*

 **R: O primeiro Oscar para melhor Atriz foi para Janet Gaynor no ano de 1927**
 
<code> select name, year_film from movies where winner= "true" and category= "Actress"; </code>

*Na coluna/campo Winner, altere todos os valores com "True" para 1 e todos os valores "False" para 0.*

<code> update movies set winner= 0 where winner= "false";
 update movies set winner= 1 where winner= "true"; </code>

*Em qual edição do Oscar "Crash" ganhou o prêmio principal?*

**R: "Crash" ganhou o prêmio de melhor filme na 78° edição do Oscar, no ano de 2006**

 <code> select * from movies where film="Crash" and winner=1 and category="BEST PICTURE"; </code>

*Na sua opinião, que filme merecia ganhar um Oscar e não ganhou?*

**R: The Imitation Game**

*Bom... dê um Oscar para esse filme, então.*

<code> update movies set winner=1 where id_movie=9718; </code>

*O filme Central do Brasil aparece no Oscar?*

**R: Não.**

<code> select * from movies where film="Central do Brasil"; </code>

*Aliás... Qual sua opinião sobre Central do Brasil?*

**R: Ainda não assisti. Pelo trailer que vi, parece um filme interessante.** 

*Inclua no banco 3 filmes que nunca nem foram nomeados ao Oscar, mas que na sua opinião, merecem.*

**R: "Modern Times";"Persuasion";"O Auto da Compadecida".**

<code> insert into movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) values (1936, 1937, 9, 'BEST PICTURE', 'Charlie Chaplin', 'Modern Times', 0);
insert into movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) values (2022,2023, 95, 'WRITING (Adaptation)', 'Jane Austen', 'Persuasion', 0 );
insert into movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) values (200,2001,72,'BEST PICTURE', 'Guel Arraes', 'O Auto da Compadecida',0 ); </code>

*Crie uma nova categoria de premiação. Qualquer prêmio que você queira dar. Agora vamos dar esses prêmios aos filmes que você cadastrou na questão acima.*

**R: Categoria: "Everyone should watch"**

<code> update movies set category= "Everyone Should Watch" where id_movie= 10397 or id_movie= 10398 or id_movie = 10399; </code>

*Qual foi o primeiro ano a ter um prêmio do Oscar?*

**R:Em 1928.**

<code> select year_film, year_ceremony from movies where winner= 1; </code>

*Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor?*

**R: O Oscar de melhor filme foi para: "Chicago"; o de melhor diretor para:"The Pianist"; e não houve prêmio de melhor de atriz.**

<code> select * from movies where category="BEST PICTURE" and year_ceremony= 2003 and winner=1 or category="DIRECTING" and year_ceremony= 2003 and winner=1 or category="ACTRESS" and year_ceremony= 2003 and winner=1 order by category; </code>

*Agora procure 7 atrizes que não sejam americanas, europeias ou brasileiras.  Vamos cadastrá-los no nosso banco, mas eles ainda não ganharam o Oscar. Só foram nomeados.*
** R:Letitia Wright, Hanggini Purinda Retto, Amy Sun, Seo Ye-ji, Gal Gadot, Pallavi Sharda e  Hazal Kaya. **

<code> insert into movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) values (2018, 2019, 91, 'ACTRESS', 'Letitia Wright', 'Black Panther', 0);
insert into movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) values (2021, 2022, 94, 'ACTRESS', 'Hanggini Purinda Retto', 'Geez & Ann', 0);
insert into movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) values (2018, 2019, 91, 'ACTRESS', 'Amy Sun', 'Accidentally in Love', 0);
insert into movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) values (2020, 2021, 92, 'ACTRESS', 'Seo Ye-ji', "It's Okay to Not Be Okay", 0);
insert into movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) values (2022, 2023, 95, 'ACTRESS', 'Gal Gadot', 'Death on the Nile', 0);
insert into movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) values (2021,2022,94,'ACTRESS', 'Pallavi Sharda', 'wedding season', 0);
insert into movies (year_film, year_ceremony, ceremony, category, `name`, film, winner) values (2022, 2023, 95, 'ACTRESS', 'Hazal Kaya', 'Midnight at the Pera Palace', 0); </code>

*Agora vamos falar da sua vida. Me diga o nome de uma pessoa que você admira e o que ela fez na sua vida. Agora me diz: Quê prêmio essa pessoa merece?*

**R: Minha vó, Maria Cristina, uma das pessoas que mais respeito e admiro!
A pessoa mais forte que conheço, sem dúvidas, depois de passar por tudo que passamos, ela ainda continua firme e forte, mesmo depois de perder a filha e o marido.
Continua de cabeça erguida e ainda consegue dar conta de tudo!
Minha vó merece tudo que há de bom nessa vida! Amo muito ela!
