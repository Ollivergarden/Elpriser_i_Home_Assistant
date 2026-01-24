# Sammanfattning
Här samlar jag kod relaterat till elpriser och optimeringar i Home Assistant.
Just nu finns 
- Elpriser-yaml, hanterar beräkning av vägda och aritmetriska elpriser på olika tider samt besparing/extrakostand beroende på när elen förbrukats
- price_opt.yaml, hanterar blockering av Nibe värmepump baserat på elpris och gradminuter
- exempel_dashboard.txt, en enkle dasboard för att visualisera ovan
  
# Beräkning elbesparing
Ett "package" för home assistant som beräknar besaring av kostnadsoptimeringar baserad på kvartspriser

*Förutsättningar*
* Du behöver mätning på din elimport
* https://www.home-assistant.io/integrations/nordpool/

# Dokumentation

Du kan läsa om bakgrund, beräkingar mm på [https://ontour.ollivergarden.se](https://www.ontour.ollivergarden.se/mata-effektiviteten-av-kostandsoptimering-av-timpriser-och-kvartspriser-med-hjalp-av-home-assistant/)

Home Assistant kan konfigureras på 3 oliika sätt, dessa kan även kombineras.
Denna fil avser hantering via paket. Om du inte jobbat med det tidigare kan du läsa om 
vad som krävs på denna sida https://ontour.ollivergarden.se ( snart )

# Blockering av bergvärmepump ( price_opt.yaml )
Ett paket för att konfigurera setup och blockera bergvärmepump vid höga priser.
Används med fördel ihop med paket för att beräkna priser och besparingar.

*Förusättningar*
* [Nibe Heatpump](https://www.home-assistant.io/integrations/nibe_heatpump/)

  
## Konfigurering
- *price_opt_limit_percent*: Vid hur många procent ner från dagens maxpris ska pumpen blockeras
- *price_opt_dm_limit*: Hur långt ner ska pumpens gradminuter ( DM ) få gå innan blockeringen avbryts ( eller inte startar )
- *price_opt_diff_limit*: Hur stor ska skillnaden mellan dagens högsta och lägsta värde vara för att det ska vara värt att försöka styra.

# Dashboard
Det finns med kod för en exempeldashboard. 
Tanken är att du i Home Assistant går till inställningar/System/Kontrollpaneler och skapar en ny
Gå till redigera kontrollpanel via pennan upp till höger
I redigeringsläge får du tre prickar uppe till höger klicka där och välj "Redigera i YAML"
Markera allt och klistra in koden härifrån
**OBS gör inte detta i din vanliga dashboard**

Sen kan du kopiera de element du är intresserade av till din ordinarie dashboard
