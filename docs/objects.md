# Objects
## Inhoudsopgave
* [`attribute`](#attribute)
* [`calamity`](#calamity)
* [`clusterPoint`](#cluster_point)
* [`clusterRange`](#cluster_range)
* [`dateRange`](#date_range)
* [`departure`](#departure)
* [`disturbance`](#disturbance)
* [`fare`](#fare)
* [`fareInfo`](#fare_info)
* [`fareLeg`](#fare_leg)
* [`introduction`](#introduction)
* [`journey`](#journey)
* [`latLong`](#lat_long)
* [`leg`](#leg)
* [`line`](#line)
* [`location`](#location)
	* [`address`](#location_address)
	* [`station`](#location_station)
	* [`stop`](#location_stop)
  	* [`street`](#location_street)
	* [`place`](#location_place)
	* [`poi`](#location_poi)
* [`ludMessage`](#lud_message)
* [`mode`](#mode)
* [`operator`](#operator)
* [`savedJourneyMutation`](#saved_journey_mutation)
* [`savedJourneyMutationResult`](#saved_journey_mutation_result)
* [`savedLocation`](#saved_location)
* [`savedLocationMutation`](#saved_location_mutation)
* [`savedLocationMutationResult`](#saved_location_mutation_result)
* [`stop`](#stop)
* [`tab`](#tab)
* [`urls`](#urls)
* [`use`](#use)
* [`usedLocation`](#used_location)

---

<a id="attribute"></a>
## Object: `attribute`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **id** | Identifier van het attribuut | String |
| **title** | Aanduiding van attribuut | String |

---

<a id="calamity"></a>
## Object: `calamity`

| Naam | Omschrijving |
|-----:|:-------------|
| **title** | Bevat de titel van de calamiteit. |
| **introduction** | Bevat een `introduction` object. |
| **textHtml** | Bevat uitleg over de calamiteit in html. |

---

<a id="cluster_point"></a>
## Object: `clusterPoint`

| Naam | Omschrijving |
|-----:|:-------------|
| **location** | Bevat een `location` object. (optioneel) |
| **fallbackPointName** | Bevat de naam van het punt indien er geen `location` beschikbaar is. |
| **fallbackPlaceName** | Bevat de naam van de plaats indien er geen `location` beschikbaar is. |

---

<a id="cluster_range"></a>
## Object: `clusterRange`

| Naam | Omschrijving |
|-----:|:-------------|
| **oneWay** | Geeft aan of het cluster range één kant op is, of beide richtingen. |
| **start** | Bevat een `clusterPoint` object. |
| **end** | Bevat een `clusterPoint` object. |

---

<a id="date_range"></a>
## Object: `dateRange`

| Naam | Omschrijving |
|-----:|:-------------|
| **from** | Geeft de minimum-datum (`yyyy-MM-dd`) aan. Er kunnen geen reizen voor deze datum gepland worden. |
| **to** | Geeft de maximum-datum (`yyyy-MM-dd`) aan. Er kunnen geen reizen na deze datum gepland worden. |

---

<a id="departure"></a>
## Object: `departure`

| Naam | Omschrijving |
|-----:|:-------------|
| **time** | Vertrektijd in het formaat `HH:mm`. |
| **destinationName** | Bevat de naam van de bestemming. |
| **viaNames** | Bevat een combinatie van de stops. |
| **mode** | Bevat een `mode` object. |
| **operatorName** | Bevat de naam van de operator. |
| **service** | Onbekend. |
| **platform** | Bevat de naam van het platform van vertrek. |
| **platformChanged** | Bevat een `boolean` die aangeeft of het platform gewijzigd is. |
| **remark** | Onbekend. |
| **realtimeState** | Geeft aan of er op tijd vertrokken wordt (zie `types.md`). |
| **realtimeText** | Bevat een verklaring, wanneer er niet op tijd vertrokken wordt. |

---

<a id="disturbance"></a>
## Object: `disturbance`

| Naam | Omschrijving |
|-----:|:-------------|
| **plannerDisturbanceId** | Unieke identifier voor deze storing. |
| **title** | Bevat de titel voor deze storing. |
| **datesString** | Bevat de datum als een tekst. |
| **startDateTime** | Bevat een datum (incl. tijd) in het formaat `yyyy-MM-ddTHH:mm`. |
| **endDateTime** | Bevat een datum (incl. tijd) in het formaat `yyyy-MM-ddTHH:mm`. |
| **cause** | Bevat de oorzaak van de storing. |
| **effect** | Bevat het effect van de storing. |
| **measure** | Onbekend. |
| **advice** | Onbekend. |
| **operatorAdvice** | Bevat de adviestekst van de operator. |
| **lines** | Bevat een array van `line` objecten. (optioneel) |
| **clusters** | Bevat een array van ... (optioneel, onbekend) |
| **clusterRanges** | Bevat een array van `clusterRange` objecten. (optioneel) |
| **alternativeClusters** | Bevat een array van ... (optioneel, onbekend) |

---

<a id="fare"></a>
## Object: `fare`

| Naam | Omschrijving |
|-----:|:-------------|
| **class** | Vertegenwoordigt de klas van deze fare. |
| **reduced** | Bevat een `boolean` die aangeeft of deze fare met of zonder korting is. |
| **eurocents** | Bevat de prijs van deze fare uitgedrukt in cent (dus x100). |

---

<a id="fare_info"></a>
## Object: `fareInfo`

| Naam | Omschrijving |
|-----:|:-------------|
| **complete** | Onbekend. |
| **fullPriceCents** | De volledige prijs voor een enkele reis, uitgedrukt in cent (dus x100). |
| **reducedPriceCents** | De volledige prijs voor een enkele reis met korting, uitgedrukt in cent (dus x100). |
| **legs** | Bevat een array van `fareLeg` objecten. |

---

<a id="fare_leg"></a>
## Object: `fareLeg`

| Naam | Omschrijving |
|-----:|:-------------|
| **from** | Bevat een `location` object dat het vertrekpunt vertegenwoordigt. |
| **to** | Bevat een `location` object dat de bestemming vertegenwoordigt. |
| **locationsString** | Bevat de combinatie van de naam van het vertrekpunt en de bestemming. |
| **modeTypeString** | Bevat het type van de mode in normale taal (incl. hoofdletter). |
| **operatorString** | Bevat de naam van de operation in normale taal (incl. hoofdletter). |
| **fares** | Bevat een array van verschillende `fare` combinaties (bv. eerste/tweede klas en met/zonder korting). |

---

<a id="introduction"></a>
## Object: `introduction`

| Naam | Omschrijving |
|-----:|:-------------|
| **title** | Bevat de titel van de introductie. |
| **textHtml** | Bevat de introductie in html formaat. |
| **imageUrl** | Bevat de url naar een afbeelding die getoond kan worden bij de introductie. |
| **imageText** | Bevat een onderschrift voor de afbeelding. |

---

<a id="journey"></a>
## Object: `journey`

| Naam | Omschrijving | Type |
|-----:|:-------------|:----|
| **id** | Unieke identifier voor deze reis. | String |
| **ludMessages** | Bevat een array van `ludMessage` objecten. | List of [LudMessage](#lud_message) |
| **fasterJourneyId** | Bevat een unieke identifier van een snellere reis. | String? |
| **departure** | Bevat een vertrekdatum (inclusief tijd) in het formaat `yyyy-MM-ddTHH:mm`. | DateTime |
| **arrival** | Bevat een aankomstdatum (inclusief tijd) in het formaat `yyyy-MM-ddTHH:mm`. | DateTime |
| **numberOfChanges** | Bevat het aantal overstappen dat in de reis gemaakt moet worden. | Integer |
| **legs** | Bevat een array van `leg` objecten. | List of [Leg](#leg) |
| **fareInfo** | Bevat een `fareInfo` object. | [FareInfo](#fare_info) |
| **occupancy** | Onbekend. | Integer |

---

<a id="lat_long"></a>
## Object: `latLong`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **lat** | Bevat de latitude van de locatie. | Float |
| **long** | Bevat de longitude van de locatie. | Float |

---

<a id="leg"></a>
## Object: `leg`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **type** | Bevat het type leg (zie `types.md` voor meer informatie). | LegType |
| **duration** | Duur van leg in de reis in format "hh:mm" | String? |
| **mode** | Bevat een `mode` object. | [Mode](#mode) |
| **destination** | Bevat de naam van de bestemming van deze leg. | String? |
| **operator** | Bevat een `operator` object. | [Operator](#operator)? |
| **service** | Nummer van het desbetreffende vervoersmiddel | Integer? |
| **attributes** | Bevat een `attribute` object.. | List of [Attribute](#attribute)? |
| **disturbancePlannerIds** | Onbekend. | |
| **serivceMessageIds** | Onbekend. | |
| **stops** | Bevat een array van `stop` objecten. | List of [Stop](#stop) |

---

<a id="line"></a>
## Object: `line`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **name** | Bevat de naam van de lijn. | String |
| **operatorName** | Bevat de naam van de operator (bv. RET) | String |
| **modeName** | Bevat de naam van de mode (bv. Metro) | String |
| **modeType** | Bevat het type van de mode (bv. Metro) | String |
| **destinationNames** | Bevat een array van namen van de bestemmingen van de lijn. | List of String |

---

<a id="location"></a>
## Object: `location`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **id** | Unieke identifier voor deze locatie. | String |
| **type** | Bevat het type locatie (zie `types.md` voor meer informatie). | LocationType |
| **name** | Bevat de naam van de locatie. | String |
| **latLong** | Bevat een `latLong` object. | [LatLong](#lat_long) |

---

<a id="location_address"></a>
## Object: `location` -> `address`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **houseNr** | Bevat het huisnummer van het adres | String |
| **place** | Bevat een `location` met als `type=place`, indien beschikbaar. | [Location -> Place](#location_place) |

---

<a id="location_station"></a>
## Object: `location` -> `station`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **stationId** | Bevat de afkorting zoals deze bekend is bij de NS. | String |
| **stationType** | Bevat het type station (zie `types.md` voor meer informatie). | StationType |
| **place** | Bevat een `location` met als `type=place`, indien beschikbaar. | [Location -> Place](#location_place) |
| **urls** | Bevat een `urls` object. | [Urls](#urls) |

---

<a id="location_stop"></a>
## Object: `location` -> `stop`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **stopType** | Type van de halte. Bijv. `Bushalte` | String |
| **place** | Bevat een `location` met als `type=place`, indien beschikbaar. | [Location -> Place](#location_place) |
| **urls** | Bevat een `urls` object. | [Urls](#urls) |

---

<a id="location_street"></a>
## Object: `location` -> `street`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **place** | Bevat een `location` met als `type=place`, indien beschikbaar. | [Location -> Place](#location_place) |

---

<a id="location_place"></a>
## Object: `location` -> `place`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **name** | Bevat de naam van de plaats. | String |
| **regionCode** | Bevat de afkorting van de provincie waar de plaats zich in bevindt. (bv. NH of UT) | String |
| **regionName** | Bevat de volledige naam van de provincie waar de plaats zich in bevindt. (bv. Noord-Holland of Utrecht) | String |
| **showRegion** | Bevat een `boolean` die aangeeft of de naam van de regio zichtbaar moet zijn in de app. | Boolean |
| **countryCode** | Bevat de afkorting van het land waar de plaats zich in bevindt. (bv. NL) | String |
| **countryName** | Bevat de volledige naam van het land waar de plaats zich in bevindt. (bv. Nederland) | String |
| **showCountry** | Bevat een `boolean` die aangeeft of de naam van het land zichtbaar moet zijn in de app. | Boolean |

---

<a id="location_poi"></a>
## Object: `location` -> `poi`

| Naam | Omschrijving |
|-----:|:-------------|
| **poiType** | Bevat het type poi (zie `types.md` voor meer informatie). |
| **place** | Bevat een `location` met als `type=place`, indien beschikbaar. |

---

<a id="lud_message"></a>
## Object: `ludMessage`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **text** | Bevat een waarschuwingstekst. | String |
| **url** | Bevat een URL naar een webpagina over de waarschuwing. | String? |

---

<a id="mode"></a>
## Object: `mode`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **type** | Bevat het type (zie `types.md` voor meer informatie). | ModeType |
| **name** | Bevat de naam van deze mode. | String |

---

<a id="operator"></a>
## Object: `operator`

| Naam | Omschrijving | Types |
|-----:|:-------------|:------|
| **type** | Bevat het type van de operator (zie `types.md` voor meer informatie). | OperatorType |
| **name** | Bevat de naam van de operator. | String |
| **contactpageurl** | Bevat een link naar het contact formulier van de operator | String |
| **code** | Bevat een unieke code voor elke operator | String |

---

<a id="saved_journey_mutation"></a>
## Object: `savedJourneyMutation`

| Naam | Omschrijving |
|-----:|:-------------|
| **id** | Bevat de unieke identifier van de reis (zie `journey`). |
| **state** | Bevat een `state` waarde (zie `types.md`). |

---

<a id="saved_journey_mutation_result"></a>
## Object: `savedJourneyMutationResult`

| Naam | Omschrijving |
|-----:|:-------------|
| **id** | Bevat de unieke identifier van de reis (zie `journey`). |

---

<a id="saved_location"></a>
## Object: `savedLocation

| Naam | Omschrijving |
|-----:|:-------------|
| **id** | Bevat de unieke identifier van de locatie (zie `location`). |
| **title** | De naam van de locatie, zoals de gebruiker die genoemd heeft. |
| **icon** | Bevat een `icon` waarde (zie `types.md`). |
| **hash** | Onbekend. |
| **location** | Bevat een `location` object. |

---

<a id="saved_location_mutation"></a>
## Object: `savedLocationMutation

| Naam | Omschrijving |
|-----:|:-------------|
| **title** | De naam van de locatie, zoals de gebruiker die genoemd heeft. |
| **id** | Bevat de unieke identifier van de locatie (zie `location`). |
| **state** | Bevat een `state` waarde (zie `types.md`). |
| **icon** |  Bevat een `icon` waarde (zie `types.md`). |

---

<a id="saved_location_mutation_result"></a>
## Object: `savedLocationMutationResult

| Naam | Omschrijving |
|-----:|:-------------|
| **id** | Bevat de unieke identifier van de locatie (zie `location`). |
| **savedLocation** | Bevat een `savedLocation` object. |

---

<a id="stop"></a>
## Object: `stop`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **arrival** | Bevat een aankomstdatum (inclusief tijd) in het formaat `yyyy-MM-ddTHH:mm`. | DateTime |
| **departure** | Bevat een vertrekdatum (inclusief tijd) in het formaat `yyyy-MM-ddTHH:mm`. | DateTime |
| **platform** | Bevat het spoor of platform waar deze trein of bus (o.i.d.) stopt. | String |
| **location** | Bevat een `location` object. | [Location](#location) |
| **fallbackName** | Onbekend. | |

---

<a id="tab"></a>
## Object: `tab`

| Naam | Omschrijving |
|-----:|:-------------|
| **id** | Unieke identifier (uniek in de bovenliggende array) van de tab. |
| **name** | Naam van de tab. |
| **locations** | Bevat een array van `location` objecten die betrekking hebben op deze tab. |
| **departures** | Bevat een array van `departure` objecten. |

---

<a id="urls"></a>
## Object: `urls`

| Naam | Omschrijving | Type |
|-----:|:-------------|:-----|
| **nl-NL** | Bevat het pad van een Nederlandse URL met betrekking tot deze locatie. | String |
| **en-GB** | Bevat het pad van een Engelse URL met betrekking tot deze locatie. | String |

---

<a id="use"></a>
## Object: `use`

| Naam | Omschrijving |
|-----:|:-------------|
| **week** | Bevat de datum van de eerste dag (maandag) van de week in het formaat `yyyy-MM-dd`. |
| **count** | Geeft het gebruik aan in die week. |

---

<a id="used_location"></a>
## Object: `usedLocation`

| Naam | Omschrijving |
|-----:|:-------------|
| **id** | Bevat de unieke identifier van een locatie die meegeleverd is in de `locations` array. |
| **uses** | Bevat een `use` object. |
