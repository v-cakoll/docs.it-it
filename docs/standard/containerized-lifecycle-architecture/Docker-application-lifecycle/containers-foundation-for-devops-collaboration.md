---
title: Contenitori come base per la collaborazione DevOps
description: Comprendere il ruolo chiave dei contenitori per semplificare DevOps.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 752a678be7735f7ae962005e1d373993d1496753
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2019
ms.locfileid: "56583732"
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a>Contenitori come base per la collaborazione DevOps

Per la natura dei contenitori e tecnologia Docker, gli sviluppatori possono condividere i software e le dipendenze con facilità con le operazioni IT e gli ambienti di produzione eliminando il tipico "funziona sul mio computer" sono più scuse:. I contenitori per risolvere i conflitti delle applicazioni tra ambienti diversi. Indirettamente, contenitori e Docker Riunisci sviluppatori e gli operatori IT più vicino, rendendo più semplice per la loro di collaborare in modo efficace. Adottare il flusso di lavoro di contenitore offre molti clienti con la continuità di DevOps che aver ricercato ma in precedenza era necessario implementare tramite la configurazione più complessa per la versione e creare pipeline. I contenitori semplificano le pipeline di compilazione, testing e distribuzione in DevOps.

![Docker consente la creazione di collegamenti tra sviluppatori e architetti nel carico di lavoro di progettazione/sviluppo e operazioni IT nel carico di lavoro di esecuzione/monitoraggio/gestione](./media/image1.png)

**Figura 2-1.** Carichi di lavoro principale per ogni "persone"dedite"del ciclo di vita per applicazioni Docker in contenitori

Con i contenitori Docker, gli sviluppatori propri ciò che è all'interno di contenitori (applicazioni e dei servizi e dipendenze per Framework e componenti) e come i contenitori e i servizi si comportano insieme come un'applicazione composta da una raccolta di servizi. Le interdipendenze di più contenitori sono definite in un `docker-compose.yml` file, o ciò che è stato definito un *manifesto della distribuzione*. Nel frattempo, i team IT (professionisti IT e gestione) possono concentrarsi sulla gestione di ambienti di produzione; infrastruttura; scalabilità; monitoraggio; e, in definitiva, assicurando che le applicazioni forniscono in modo corretto per gli utenti finali, senza dover conoscere il contenuto dei contenitori diversi. Di conseguenza, il nome "contenitore," si richiama la stessa analogia ai contenitori di spedizione del mondo reale. Di conseguenza, i proprietari del contenuto del contenitore necessitano non riguardano autonomamente con modalità verrà spedito il contenitore e i trasporti della società per la spedizione un contenitore dal relativo punto di origine alla destinazione senza conoscere o il contenuto necessario. In modo analogo, gli sviluppatori possono creare e possedere il contenuto all'interno di un contenitore Docker senza la necessità di occuparsi di meccanismi di "transport".

In pillar sul lato sinistro della figura 2-1, gli sviluppatori di scrivano ed eseguire il codice localmente nei contenitori Docker con Docker per Windows o Mac. Definiscono l'ambiente operativo per il codice usando un Dockerfile che specifica il sistema operativo di base per l'esecuzione, nonché i passaggi di compilazione per compilare il codice in un'immagine Docker. Gli sviluppatori di definiscono come uno o più immagini in grado di interagire con citato in precedenza `docker-compose.yml` manifesto di distribuzione di file. Quando vengono completate relativi allo sviluppo locale, essi push codice delle proprie applicazioni e i file di configurazione di Docker nel repository di codice di propria scelta (vale a dire, archivio Git).

La colonna di DevOps definisce le pipeline di integrazione compilazione – Continuous usando il documento Dockerfile fornito nel repository del codice. Il sistema CI effettua il pull di immagini contenitore di base dal registro Docker selezionato e compila le immagini Docker personalizzate per l'applicazione. Le immagini vengono quindi convalidate e il push nel Registro di sistema Docker usata per le distribuzioni in più ambienti.

Nella colonna a destra, i team di gestire operazioni distribuito applicazioni e dell'infrastruttura nell'ambiente di produzione durante il monitoraggio di applicazioni e l'ambiente in modo che possano fornire commenti e suggerimenti e informazioni dettagliate per il team di sviluppo sul modo in cui l'applicazione potrebbe risultare migliorata. App contenitore in genere vengono eseguite nell'ambiente di produzione usando gli agenti di orchestrazione.

I due team collaborano attraverso una piattaforma di base (contenitori di Docker) che fornisce una separazione delle problematiche come contratto, migliorando notevolmente la collaborazione dei due team nel ciclo di vita dell'applicazione. Gli sviluppatori proprietari i contenuti del contenitore, del relativo ambiente operativo e le interdipendenze di contenitore, mentre i team operativi adottare le immagini predefinite con il manifesto ed eseguiti nel sistema di orchestrazione.

## <a name="challenges-in-application-life-cycle-when-using-docker"></a>Quando si usa Docker del ciclo di sfide nel ciclo di vita dell'applicazione.

Esistono molte buone ragioni che consentirà di aumentare il numero di applicazioni in contenitori nei prossimi anni, e uno dei motivi seguenti è la creazione di applicazioni basate su microservizi.

Durante gli ultimi 15 anni, l'uso dei servizi web è stata la base di migliaia di applicazioni, e probabilmente, dopo pochi anni, si troverà la stessa situazione con le applicazioni basate su microservizi in esecuzione nei contenitori Docker.

È inoltre importante ricordare che è anche possibile usare i contenitori Docker per applicazioni monolitiche e otterrai comunque la maggior parte dei vantaggi di Docker. I contenitori non scelgono microservizi solo.

L'uso di Docker contenitori e microservizi cause nuove sfide nel processo di sviluppo della tua organizzazione e di conseguenza, è necessario una solida strategia per gestire molti contenitori e microservizi in esecuzione su sistemi di produzione. Infine, le applicazioni aziendali avranno centinaia o migliaia di contenitori o le istanze in esecuzione nell'ambiente di produzione.

Queste sfide creare nuovi problemi quando si usano strumenti DevOps, pertanto sarà necessario definire i nuovi processi nelle attività DevOps, e trovare le risposte per questo tipo di domande:

- Quali strumenti è possibile utilizzare per lo sviluppo, per operazioni, gestione e integrazione continua/recapito Continuo?

- Come la mia azienda gestire gli errori nei contenitori durante l'esecuzione nell'ambiente di produzione?

- Come è possibile modificare parti di prodotti software nell'ambiente di produzione con tempo di inattività minimo?

- Come ridimensionare e come è possibile monitorare il nostro sistema di produzione?

- Come possiamo includiamo test e la distribuzione di contenitori nella nostra pipeline di rilascio?

- Come è possibile usare strumenti Open Source/le piattaforme per i contenitori in Microsoft Azure?

Se è possibile rispondere a tutte queste domande, sarà meglio preparati a spostare le applicazioni (app nuova o esistente) per i contenitori Docker. 

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a>Introduzione a un generico end-to-end Docker applicazione ciclo di vita del flusso di lavoro

Figura 2-2 presenta un flusso di lavoro più dettagliato per un ciclo di vita delle applicazioni di Docker, con particolare attenzione in questa istanza in asset e attività DevOps specifiche.

![Questo diagramma mostra il ciclo"esterno" della metodologia DevOps. Quando viene eseguito il push di codice al repository, viene avviata una pipeline di integrazione continua, quindi inizia la pipeline di recapito Continuo, in cui viene distribuita l'applicazione. Metriche raccolte dalle applicazioni distribuite vengono inserite nuovamente il carico di lavoro di sviluppo, in cui si verifica il "ciclo interno", in modo che i team di sviluppo hanno dati effettivi per soddisfare le esigenze dell'utente finale e.](./media/image2.png)

**Figura 2-2.** Flusso di lavoro generale per il ciclo di vita dell'applicazione in contenitori Docker

Tutto quello che inizia con lo sviluppatore, che avvia la scrittura di codice del flusso di lavoro ciclo interno. La fase del ciclo interno è in cui gli sviluppatori di definiscono tutti gli elementi che si verifica prima il push del codice nel repository di codice (ad esempio, un sistema di controllo sorgente come Git). Dopo aver eseguito il commit, il repository trigger integrazione continua (CI) e il resto del flusso di lavoro.

Il ciclo interno consiste essenzialmente i passaggi tipici, ad esempio "code", "Esegui", "test" e "debug", nonché i passaggi aggiuntivi necessari subito prima di eseguire l'app in locale. Si tratta di processo per gli sviluppatori per eseguire e testare l'app come un contenitore Docker. Il flusso di lavoro ciclo interno verrà descritta nelle sezioni che seguono.

Un passo indietro a esaminare il end-to-end del flusso di lavoro, il flusso di lavoro di DevOps è più di una tecnologia o un set di strumenti: è un'attitudine che richiede l'evoluzione relative alla lingua. È persone, processi e gli strumenti appropriati per rendere il ciclo di vita dell'applicazione più veloce e più prevedibile. Le aziende che adottano un flusso di lavoro in contenitori in genere ristrutturare le organizzazioni per rappresentare le persone e processi che corrispondono al flusso di lavoro in contenitori.

Mettendo in pratica DevOps può aiutare i team rispondono più velocemente insieme a pressioni competitive sostituendo i processi manuali soggette a errori grazie all'automazione, con conseguente miglioramento della tracciabilità e flussi di lavoro ripetibile. Le organizzazioni possono anche gestire gli ambienti in modo più efficiente e realizzare risparmi sui costi con una combinazione di risorse cloud e locale nonché strettamente integrati.

Quando si implementa il flusso di lavoro DevOps per le applicazioni di Docker, si noterà che le tecnologie di Docker siano presenti in quasi tutte le fasi del flusso di lavoro, dalla casella di sviluppo durante l'uso nel ciclo interno (codice, esecuzione, debug), la fase di compilazione-test-integrazione continua e, Infine, la distribuzione dei contenitori per gli ambienti di staging e produzione.

Miglioramento delle procedure consigliate di qualità aiuta a identificare i difetti nelle prime fasi del ciclo di sviluppo che riduce il costo della correzione degli errori. Tra cui l'ambiente e le dipendenze nell'immagine e adottando una filosofia di distribuire la stessa immagine tra più ambienti, si Alza di livello una disciplina di estrarre le configurazioni specifiche dell'ambiente rende le distribuzioni più affidabile.

Avanzata dei dati ottenuti tramite la strumentazione effettiva (monitoraggio e diagnostica) forniscono informazioni dettagliate su problemi di prestazioni e comportamento degli utenti per guidare gli investimenti e le priorità delle future.

DevOps deve essere considerate un viaggio, non una destinazione. Si devono essere implementato in modo incrementale per i progetti in modo appropriato con ambiti da cui è possibile dimostrare, informazioni e si evolvono.

## <a name="benefits-of-devops-for-containerized-applications"></a>Vantaggi di DevOps per le applicazioni nei contenitori

Ecco alcune delle più importanti vantaggi forniti da un flusso di lavoro di DevOps a tinta unita:

- Distribuire il software di qualità migliore, più velocemente e con una migliore conformità.

- Versioni precedenti e più economico di unità rettifiche e il miglioramento continuo.

- Aumentare la trasparenza e la collaborazione tra gli stakeholder coinvolti nella distribuzione e il funzionamento del software.

- Controllare i costi e utilizzo delle risorse sottoposte a provisioning in modo più efficace, riducendo al minimo i rischi di sicurezza.

- Plug and play bene per molti dei tuoi investimenti esistenti di DevOps, tra cui investimenti in open source.

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](../Microsoft-platform-tools-containerized-apps/index.md)
