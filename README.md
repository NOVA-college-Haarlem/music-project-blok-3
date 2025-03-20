# Project Music Album

## Opdrachten

### Opdracht 1 - Database ontwerp

- Maak op basis van onderstaande userstories en het SQL-bestand een database ontwerp. 

### Opdracht 2 - Repository

- Maak gebruik van de repository: https://github.com/NOVA-college-Haarlem/music-project-blok-3
- Fork de repository
- Clone de repository

### Opdracht 3 - Website
 
- Maak een website voor een muziekalbum.

### Opdracht 4 - Controleren

- Controleer je website door gebruik te maken van de rubric.

## Userstories

### Overzichtspagina

**Als een** bezoeker  
**Wil ik** een overzicht zien van alle beschikbare muziekalbums  
**Zodat ik** snel kan bladeren door verschillende albums

**Als een** bezoeker  
**Wil ik** basisinformatie zien van elk album (titel, artiest, thumbnail afbeelding)  
**Zodat ik** een eerste indruk krijg zonder naar de detailpagina te hoeven gaan

**Als een** bezoeker  
**Wil ik** op een album kunnen klikken  
**Zodat ik** naar de detailpagina kan gaan voor meer informatie

## Filtering

**Als een** bezoeker  
**Wil ik** kunnen filteren op muziekgenre (pop, rock, jazz, etc.)  
**Zodat ik** alleen albums zie die passen bij mijn muziekvoorkeur

**Als een** bezoeker  
**Wil ik** kunnen filteren op artiest  
**Zodat ik** albums kan vinden van artiesten die ik waardeer

### Overige Functionaliteiten

**Als een** bezoeker  
**Wil ik** kunnen sorteren op releasedate (van nieuw naar oud of oud naar nieuw)  
**Zodat ik** de nieuwste albums of juist klassiekers kan vinden

**Als een** bezoeker  
**Wil ik** zien hoeveel resultaten er beschikbaar zijn binnen mijn gekozen filters  
**Zodat ik** weet hoeveel opties ik heb

## SQL-bestand

```sql

-- Database schema voor Music Album Database met één tabel

-- Albums tabel
CREATE TABLE albums (
    id INT PRIMARY KEY AUTO_INCREMENT,
    titel VARCHAR(200) NOT NULL,
    artiest VARCHAR(100) NOT NULL,
    genre VARCHAR(50) NOT NULL,
    label VARCHAR(100),
    releasedate DATE,
    aantal_nummers INT,
    speelduur VARCHAR(10), -- in formaat MM:SS
    beschrijving TEXT,
    prijs DECIMAL(10, 2),
    thumbnail_url VARCHAR(255)
);

-- Voorbeelddata invoegen
INSERT INTO albums (titel, artiest, genre, label, releasedate, aantal_nummers, speelduur, beschrijving, prijs, thumbnail_url) VALUES 
('Thriller', 'Michael Jackson', 'Pop', 'Epic Records', '1982-11-30', 9, '42:19', 'Het bestverkochte album aller tijden met hits als Billie Jean en Beat It.', 19.99, 'thriller.jpg'),
('The Dark Side of the Moon', 'Pink Floyd', 'Rock', 'Harvest Records', '1973-03-01', 10, '42:49', 'Een conceptalbum over universele thema\'s zoals conflict, hebzucht, tijd en geestelijke gezondheid.', 21.99, 'darkside.jpg'),
('Back to Black', 'Amy Winehouse', 'Soul', 'Island Records', '2006-10-27', 11, '34:57', 'Het tweede en laatste studioalbum van Amy Winehouse met hits als Rehab en Back to Black.', 17.99, 'backtoblack.jpg'),
('21', 'Adele', 'Pop', 'XL Recordings', '2011-01-24', 11, '48:12', 'Een album geïnspireerd door de breuk met haar ex-vriend, met hits als Rolling in the Deep en Someone Like You.', 15.99, 'adele21.jpg'),
('Nevermind', 'Nirvana', 'Grunge', 'DGC Records', '1991-09-24', 12, '42:38', 'Het album dat grunge mainstream maakte, met de hit Smells Like Teen Spirit.', 16.99, 'nevermind.jpg'),
('Kind of Blue', 'Miles Davis', 'Jazz', 'Columbia Records', '1959-08-17', 5, '45:44', 'Een van de meest invloedrijke jazzalbums ooit, bekend om zijn improvisaties.', 18.99, 'kindofblue.jpg'),
('Abbey Road', 'The Beatles', 'Rock', 'Apple Records', '1969-09-26', 17, '47:23', 'Het laatste album dat The Beatles samen opnamen, met klassiekers als Come Together en Here Comes the Sun.', 22.99, 'abbeyroad.jpg'),
('Rumours', 'Fleetwood Mac', 'Rock', 'Warner Bros. Records', '1977-02-04', 11, '39:43', 'Een album ontstaan tijdens turbulente relaties tussen de bandleden, met hits als Go Your Own Way en Dreams.', 18.99, 'rumours.jpg'),
('The Miseducation of Lauryn Hill', 'Lauryn Hill', 'R&B', 'Ruffhouse Records', '1998-08-25', 16, '77:39', 'Een album dat soul, hip-hop en reggae combineert, met de hit Doo Wop (That Thing).', 14.99, 'miseducation.jpg'),
('Purple Rain', 'Prince', 'Pop', 'Warner Bros. Records', '1984-06-25', 9, '43:55', 'De soundtrack bij de gelijknamige film, met hits als When Doves Cry en Let\'s Go Crazy.', 19.99, 'purplerain.jpg'),
('OK Computer', 'Radiohead', 'Alternative', 'Parlophone', '1997-05-21', 12, '53:21', 'Een experimenteel album dat kritiek levert op consumentisme en technologische afhankelijkheid.', 20.99, 'okcomputer.jpg'),
('The Chronic', 'Dr. Dre', 'Hip-hop', 'Death Row Records', '1992-12-15', 16, '62:52', 'Een invloedrijk album dat G-funk introduceerde met gastoptredens van Snoop Dogg.', 13.99, 'chronic.jpg'),
('Born to Run', 'Bruce Springsteen', 'Rock', 'Columbia Records', '1975-08-25', 8, '39:26', 'Het doorbraakalbum van Springsteen met epische composities over de Amerikaanse droom.', 17.99, 'borntorun.jpg'),
('Blue', 'Joni Mitchell', 'Folk', 'Reprise Records', '1971-06-22', 10, '35:41', 'Een intiem en persoonlijk album dat wordt beschouwd als een van de beste albums aller tijden.', 16.99, 'blue.jpg'),
('Random Access Memories', 'Daft Punk', 'Electronic', 'Columbia Records', '2013-05-17', 13, '74:24', 'Een ode aan de muziek uit de jaren 70 en 80 met de hit Get Lucky.', 19.99, 'ram.jpg');
```

# Beoordelingscriteria

## Overzichtspagina
| Criterium                     | Onvoldoende                                 | Voldoende                                       | Goed                                                                      |
| ----------------------------- | ------------------------------------------- | ----------------------------------------------- | ------------------------------------------------------------------------- |
| Basisweergave van albums      | Albums worden niet of nauwelijks getoond    | Albums worden correct weergegeven               | Albums worden aantrekkelijk weergegeven met duidelijke visuele hiërarchie |
| Filter op genre               | Filter werkt niet of met ernstige fouten    | Filter werkt, maar heeft kleine gebreken        | Filter werkt perfect en is gebruiksvriendelijk                            |
| Filter op artiest             | Filter werkt niet of met ernstige fouten    | Filter werkt, maar heeft kleine gebreken        | Filter werkt perfect en is gebruiksvriendelijk                            |
| Sortering op releasedate      | Sortering werkt niet of met ernstige fouten | Sortering werkt, maar heeft kleine gebreken     | Sortering werkt perfect en is gebruiksvriendelijk                         |
| Doorklikken naar detailpagina | Links werken niet of met ernstige fouten    | Links werken, maar zijn niet optimaal geplaatst | Links werken perfect en zijn intuïtief                                    |

## Detailpagina
| Criterium                       | Onvoldoende                               | Voldoende                          | Goed                                                   |
| ------------------------------- | ----------------------------------------- | ---------------------------------- | ------------------------------------------------------ |
| Weergave van album details      | Details worden niet of nauwelijks getoond | Details worden correct weergegeven | Details worden uitgebreid en aantrekkelijk weergegeven |
| Teruglink naar overzichtspagina | Link werkt niet of is niet aanwezig       | Link is aanwezig en werkt          | Link is duidelijk zichtbaar en gebruiksvriendelijk     |

## Algemene aspecten
| Criterium          | Onvoldoende                                | Voldoende                                      | Goed                                           |
| ------------------ | ------------------------------------------ | ---------------------------------------------- | ---------------------------------------------- |
| Database connectie | Query's werken niet of met ernstige fouten | Query's werken, maar zijn niet geoptimaliseerd | Query's werken goed en zijn geoptimaliseerd    |
| Code kwaliteit     | Rommelige code met veel fouten             | Redelijk nette code met enkele fouten          | Nette, goed gestructureerde code zonder fouten |
