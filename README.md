# iOS kurs

### Del 1
- Intro til swift

### Del 2 - Gjett tallet
- Bli kjent med Xcode
##### Oppgaver
1.  Generer et tall mellom 1 og 100 ved oppstart av appen
    * Sjekk ut `arc4random_uniform(100)`
2. Gjør det mulig å gjette tallet du genererte med input fra `UITextField` ved klikk på knappen (`UIButton`). 
3.  Gi en respons i output-feltet `UILabel` (For høyt, for lavt, korrekt)
4.  Legg til en ny `UILabel` som viser hvor mange forsøk du bruker på å gjette.
5.  Generer et nytt tall hvis du gjetter riktig

### Del 3 - Pokédex
- Liten nettverks-demo
1. Sett opp et nytt Xcode prosjekt
2. Sett opp et view i InterfaceBuilder med et inputfelt `UITextField`, en knapp `UIButton` og 3 output-felt `UILabel`, og lag lenker til tilhørende `UIViewController`
3. Inputfeltet skal kun være tall mellom 1 - 151. Legg til en validator ved klikk på knappen
4. Sett opp et nettverkskall mot pokeapiet
    * GET request
    * BaseURL: `http://pokeapi.co/api/v2`
    * Hent ut informasjon om pokemon nr 1. `/pokemon/1/`
    * Noen nyttige klasser for nettverk: `URL`, `URLRequest`, `URLSession`, `URLSessionDataTask`
    * Noen nyttige klasser for JSON-parsing: `JSONDecoder`, selvlagde `struct`'s som arver `Codable` protokollen:
```sh
struct Pokemon: Codable {
    name: String
}
```

5. Oppdater nettverkskallet slik at ved klikk på knappen, skal du:
    * Laste ned informasjon om pokemonen med ID lik tallet i inputfeltet
    * Vise navnet og vekten i to av output-feltene
6. Vis HP (helse) i det tredje output feltet 
    * Tips: `stats.stat.name = hp`
7. Legg til et `UIImageView` i appen din (i InterfaceBuilder), og link det opp.
8. Sett opp et nytt nettverkskall som henter bildet av pokemonen
    * Url fra `sprites. front_default`
    * Vis bildet i `UIImageView`-et du satte opp i forrige punkt
9. Legg til en spinner som vises når du laster inn info 
    * `UIActivityMonitor`
10. Legg til en ny knapp `UIButton`, som senere skal ta deg til en ny side
11. Opprett en ny `UIViewController` fil for den nye siden, derretter presenter denne viewcontrollern ved klikk på knappen fra forrige oppgave
    * `present(viewControllerToPresent:, animated:, completion:)`
12. Legg til en knapp på den nye ViewControllern som lukker viewet og tar deg tilbake
13. Vis utfyllende info om valgt pokemon på den nye siden
    * Sjekk f.eks ut `/evolution-chain/{id}`
