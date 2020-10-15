# HoloLens 2 realisatie voor het zoeken in een Database

Dit concept is ontwikkeld door Jesse van der Elst voor een afstudeeropdracht van ICT Group. Tijdens het afstudeeronderzoek is er onderzocht hoe een interface van een HoloLens 2 eruit kan zien wanneer het gebruikt wordt om een specifiek product te zoeken. In dit bestand staan de verschillende functies die te gebruiken zijn om het bedachte interface te realiseren

## Benodigdheden
Microsoft heeft verschillende functies geschreven die gebruikt kunnen worden om een HoloLens applicatie te ontwikkelen. Om de functies te gebruiken moet eerst de Library gedownload worden. (https://github.com/microsoft/MixedRealityToolkit-Unity/releases/download/v2.4.0/Microsoft.MixedReality.Toolkit.Unity.Foundation.2.4.0.unitypackage)

## Drukbare knop

#### PressableButtonHoloLens2.cs
Deze functie maakt het mogelijk om een knop te laten werken door directe aanraking. Om de gebruiker feedback te geven is er voor gekozen om een geluid of te spelen wanneer de knop wordt ingedrukt. Dit is mogelijk wanneer wordt ingesteld `Button pressed Runtime Only: Audiosource.Playoneshot`

#### Interactable.cs
Deze functie zorgt ervoor dat de applicatie kan reageren op het indrukken van de knop. Bij deze applicatie is ervoor gekozen om het 1e scherm te laten verdwijnen en het 2 scherm zichtbaar te laten worden, dit is mogelijk door:
```c#
Onclick:
Runtime only: Scherm1 GameObject.SetActive [ ] // Scherm 1 verdwijnt
Runtime only: Scherm2 GameObject.SetActive [✓] // Scherm 2 wordt zichtbaar

```


## Scrol object

#### ScrollObjectCollection.cs
Deze functie is nodig om een scroll object te laten functioneren. 
`Scroll Direction: Left and Right` zorgt ervoor dat het alleen mogelijk is om horizontaal te scrollen
`Type of Velocity: No Velocity snap to item` zorgt ervoor dat de items vastklikken

## Directe manipulatie
Om een object te kunnen manupileren door handbewegingen zijn er drie functies nodig die toegevoegd moeten worden aan het desbetreffende object. In dit geval is het een koptelefoon. Om het obect ook te kunnen ronddraaien moet de functie `RotationAxisConstraint.cs`worden toegevoegd.

#### ObjectManupilator.cs
Deze functie maakt het mogelijk om de positie van het object te veranderen. `Host transform` zorgt ervoor dat het oject waar hierin wordt verwezen bewogen wordt. In dit geval is dat het koptelefoon object.

#### NearInteractionGrabble.cs
Deze functie is gemaakt om directe interactie te kunnen hebben met een object. Dit is mogelijk om met de hand het object vast te pakken en te verslepen naar een gewenste plek. 

#### RotationAxisConstraint.cs
Deze functie is gemaakt om een object te kunnen ronddraaien. Wanneer een object wordt vastgepakt kan het rondgedraaid worden door het draaien van de pols. 

## Eigenschappen aanwijzen op koptelefoon

#### Tooltip.cs
Deze functie is nodig om een aanwijzing mogelijk te maken. `Tool Tip Text` is het blokje waar je kan invullen welke eigenschap er zichtbaar moet worden. Verder kan de stijl van het eigenschapblokje aangepast worden. Er kan gekozen worden om een blauwe achtergrond aan het blokje te geven.

#### ToolTipConnector.cs
Deze functie is bedoeld om aan te geven welk aan welk onderdeel de eigenschap gekoppeld moet worden. Zo moet voor de eigenschap Microfoon `Target: Mic`



