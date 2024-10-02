## Aandachtspunten

### Inhoud

- Alle randvoorwaarden zijn voldaan.

- Er wordt gebruik gemaakt van Dependency Injection via de constructor (OF via @Autowired, maar dat heeft niet de voorkeur

- Er zijn Entities gemaakt voor Television, CiModule, WallBracket en RemoteController die inhoudelijk overeenkomen met de opdrachtbeschrijving

- Er is een OneToOne relatie tussen Television en RemoteController. De relatie staat maar aan 1 kant, als de relatie aan 2 kanten staat (dus in beide klassen een @OneToOne), dan heeft een van beide kanten ook een "mappedBy"
- Er is een ManyToOne relatie tussen CiModule en Television. In de Television klasse staat de @ManyToOne annotatie met optioneel de fetchtype en cascade en ook optioneel een @JoinColumn. In de CiModule klasse staat optioneel een @OneToMany annotatie. Als deze er staat, moet  deze een "mappedBy" hebben.
- Er is een @ManyToMany relatie tussen Television en WallBracket. Optioneel staat deze annotatie aan beide kanten, als dat zo is, dan heeft een van beide kanten verplicht een "mappedBy". Optioneel kan de andere kan een @JoinTable annotatie hebben (om de tabelnaam en kolom namen van de join tabel aan te passen)

- De service-laag verstuurd geen Entity objecten naar de controller, enkel TelevisionDto’s

- In de Dto klasse worden validatie annotaties gebruikt 

- Er zijn speciale endpoints om relaties te leggen. Relaties worden niet meteen in de reguliere POST methode gemaakt.(Dat kan wel, maar niet in deze casus)


### Vorm

- Let op goede naamgeving (zoals camel case en naam die bij de functionaliteit past)
- Let op witruimtes in de code. Is het goed leesbaar, of mag het wat beter geformat worden?
- Let op niet overmatig gebruik van nesting
- Let op dat de methodes niet te lang zijn
- Let op goed REST toepassing, zoals het pad, de HTTP methode en de status code.