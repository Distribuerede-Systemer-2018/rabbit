## Opgaver for i dag (13. september)

### 1. Installer og test rabbitmq 
Følg guiden på https://www.rabbitmq.com/tutorials/tutorial-one-java.html til at installere rabbitmq, og lav en consumer og producer der kan snakke sammen (hvis i er mere konfortable i et andet sprog end java bruger i også bare det).

Test forskellige scenarier - Hvad sker der hvis:
* Consumer startes først
* Producer startes først
* Der startes flere consumere, derefter en producer, og omvendt

### 2. RPC
Hvad skal der til for at en consumer kan sende et svar tilbage? 

Brug et par minutter til at tænke over det før du snyder og læser https://www.rabbitmq.com/tutorials/tutorial-six-java.html

Brug det du har lært til at lave en consumer som kan sende et resultat tilbage til klienten. Det kunne fx. være at produceren sender et tal, og consumeren ganger det med to og sender svaret tilbage. 
Du behøver ikke at lave en client klasse du kan kalde en metode på som i tutorialen, du skal blot kunne indtaste en værdi i konsollen og udskrive det svar der kommer tilbage.

Prøv derefter at tilføje en forsinkelse til consumeren, for at simulere en langsom server. Det kan fx gøres med `Thread.sleep((double) Math.random() * 10000);`

Start nu 3 consumere. Sørg for at hver consumer kun læser en besked af gangen (se kode-snippet i afsnittet 'Message acknowledgement' på https://www.rabbitmq.com/tutorials/tutorial-two-java.html. 

Start en enkelt consumer og send tre forespørgsler afsted hurtigt efter hinanden. Kommer svarene altid i samme rækkefølge som forespørgslen? Hvordan sikrer i jer, at et svar kædes sammen med det rigtige spørgsmål?
