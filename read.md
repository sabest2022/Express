Server side:
Jag har en index.js till alla funktioner som krävs för att hantera inkommande request till servern: fösta endpointen är rooten som skickar en index.html fil till klienten.

sen har vi en GET funktion som tar in en id från klienten, och svarar requesten med en json, om id finns då får man tillbaka respektiv info smat bilden, annars skickas en 404 error som säger att produkten inte finns i databasen.

Sen har vi ett POST verb som får in alla 5 egenskapaer includerad url till bilden, om id finns i databasen får man en error 401, som betyder att man inte får spara producten med den befintlig id och skall en annan id väljas,

Nästa funktion är PUT som uppdaterar en produkt med alla nya egenskaper, återigen får man error kod 404 om man väljer en id som inte finns i databasen.

Sista funktionen är DELETE, klienten skickar en id till servern för att ta bort en produkt, först får man en varning(från klient sidan) att bekräftar hen kommer att ta bort en produkt, om man godkänner, skickas id till servern, om id finns i databasen, tas boort och får klienten bekräftelse, om det inte finns på databasen får man error 404 som visar att produkten inte finns på databasen. 

Klient side:
Jag har inte haft för lång kod så skrivit script och stylen i html filen.
Jag har fem input till 5 egenskaperna och fyra knap till fyra funktionerna.
I script delen har jag några funktioner, myfunc() är första funktionen som får in alla egenskaper fråm inputerna och skapar en standard json object(stringified). Detta används av PUT och POST.
den finns en reset() funktion som nollställa alla inputerna efter man klickar på de och får svar från server.
det finns en funktion setvalue() som får in egenskaper och skapar json objecten med hjälp av myfunc().
Det finns POST, GET, PUT, DELETE funktioner som skciar en fetch till servern och får tillbaka svaren. Get funktionen har mer kod för att visa en finnare output. 
det finns också några style som visar en finnare sidan till klienten.

REST:
Det finns en REST fil som har test till alla funktionerna. det finns också test som visar error koderna.

JSON fil: json filen är under public map och alla produkt/egenskaperna sparas och updateras i den filen.

INTERNET access: Jag möjliggjorde servern på internet, då har man tillgång till servern som levererar index.htmlen direct till klienten på denna ip addres: 37.46.166.164 när min dator är uppe då får man jobba på servern direct via internet.
