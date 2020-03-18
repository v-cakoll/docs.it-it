---
title: Contenitori come base per la collaborazione DevOps
description: Informazioni sul ruolo chiave dei contenitori per la semplificazione di DevOps.
ms.date: 02/15/2019
ms.openlocfilehash: 8258f4331212d92376d64fef318adcdff492f61f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73094492"
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a>Contenitori come base per la collaborazione DevOps

Per la natura stessa dei contenitori e della tecnologia Docker, gli sviluppatori possono condividere facilmente i software e le dipendenze con il settore delle operazioni IT e gli ambienti di produzione, eliminando le classiche scuse di tipo "sul mio computer funziona". I contenitori risolvono i conflitti delle applicazioni tra ambienti diversi. Indirettamente, i contenitori e i Docker integrano l'ambiente di sviluppo e il settore delle operazioni IT, facilitando la collaborazione in modo efficace. L'adozione del flusso di lavoro con i contenitori offre a molti clienti la continuità DevOps che desideravano, ma che in precedenza doveva essere implementata con configurazioni più complesse per le pipeline di compilazione e rilascio. I contenitori semplificano le pipeline di compilazione/testing/distribuzione nel settore DevOps.

![Diagramma che mostra la proprietà del ciclo di vita di un'app Docker.](./media/containers-foundation-for-devops-collaboration/persona-workloads-docker-container-lifecycle.png)

**Figura 2-1.** Carichi di lavoro principali per "persona" nel ciclo di vita per le applicazioni Docker nei contenitori

Con i contenitori Docker, gli sviluppatori sono proprietari di ciò che è all'interno dei contenitori (applicazione, servizio e dipendenze da framework e componenti) e l'interazione tra contenitori e servizi come un'applicazione composta da una raccolta di servizi. Le interdipendenze di più contenitori sono definite in un file `docker-compose.yml`, che può essere definito un *manifesto della distribuzione*. Nel frattempo, i team di operazioni IT (professionisti IT e gestione) possono concentrarsi sulla gestione degli ambienti di produzione (infrastruttura, scalabilità, monitoraggio) e garantire che le applicazioni siano rese disponibili in modo ottimale agli utenti, anche senza che il team conosca il contenuto dei vari contenitori. Da qui il nome "contenitore", un elemento destinato a contenere altri elementi. Così i proprietari del contenuto di un contenitore non devono preoccuparsi di come verrà inoltrato, mentre l'entità responsabile del trasporto lo sposterà dal punto di origine alla destinazione senza conoscere o preoccuparsi del contenuto. In modo analogo gli sviluppatori possono creare e assumere la proprietà del contenuto di un contenitore Docker senza doversi preoccupare dei meccanismi di "trasporto".

Nel riquadro sul lato sinistro della figura 2-1 gli sviluppatori scrivono ed eseguono localmente il codice nei contenitori Docker con Docker per Windows o Mac. Definiscono l'ambiente operativo per il codice usando un Dockerfile che specifica il sistema operativo di base per l'esecuzione, nonché i passaggi necessari per la compilazione del codice in un'immagine Docker. Gli sviluppatori definiscono l'interazione tra più immagini con il manifesto della distribuzione file `docker-compose.yml` citato in precedenza. Man mano che completano lo sviluppo locale, eseguono il push del codice dell'applicazione e dei file di configurazione Docker nel repository di codice desiderato (in questo caso il repository Git).

Il riquadro DevOps definisce le pipeline compilazione-integrazione continua (CI, Continuous Integration) usando il documento Dockerfile incluso nel repository del codice. Il sistema CI esegue il pull delle immagini contenitore di base dal registro Docker selezionato e compila le immagini Docker personalizzate per l'applicazione. Le immagini vengono quindi convalidate e ne viene eseguito il push nel registro Docker usato per le distribuzioni in più ambienti.

Nel riquadro a destra i team di operazioni gestiscono le applicazioni e l'infrastruttura distribuiti in produzione, monitorando nel contempo l'ambiente e le applicazioni, per garantire la trasmissione al team di sviluppo di feedback e approfondimenti relativi a possibili miglioramenti dell'applicazione. Le app contenitore vengono in genere eseguite nell'ambiente di produzione usando gli agenti di orchestrazione.

I due team collaborano attraverso una piattaforma di base (i contenitori Docker) che offre una separazione delle problematiche per contratto, migliorando notevolmente la collaborazione dei due team nel ciclo di vita dell'applicazione. Gli sviluppatori sono responsabili dei contenuti del contenitore, del suo ambiente operativo e delle sue interdipendenze, mentre i team di operazioni IT usano le immagini compilate e il manifesto per l'esecuzione nel sistema di orchestrazione.

## <a name="challenges-in-application-life-cycle-when-using-docker"></a>Sfide nel ciclo di vita dell'applicazione associate all'uso di Docker.

Esistono molti motivi per pensare che il numero di applicazioni incluse in contenitori crescerà nei prossimi anni, e una di queste è la creazione di applicazioni basate su microservizi.

Negli ultimi 15 anni l'uso dei servizi Web è stato alla base di migliaia di applicazioni ed è probabile che tra qualche anno la situazione si ripeta con le applicazioni basate su microservizi in esecuzione nei contenitori Docker.

È anche importante ricordare che i contenitori Docker possono essere usati anche per applicazioni monolitiche, continuando a offrire comunque la maggior parte dei vantaggi dell'approccio Docker. I contenitori non sono orientati solo ai microservizi.

L'uso dei contenitori Docker e dei microservizi origina nuove sfide nel processo di sviluppo delle organizzazioni e pertanto è necessaria una strategia solida per la gestione di molti contenitori e microservizi eseguiti nei sistemi di produzione. A un dato momento le applicazioni aziendali avranno centinaia o migliaia di contenitori o istanze in esecuzione nell'ambiente di produzione.

Queste sfide creano nuovi problemi per l'uso degli strumenti DevOps, pertanto sarà necessario definire nuovi processi nelle attività DevOps e trovare risposte a domande di questo tipo:

- Quali strumenti è possibile usare per lo sviluppo, per CI/CD, per la gestione e per le operazioni IT?

- In che modo l'azienda gestirà gli errori nei contenitori durante l'esecuzione nell'ambiente di produzione?

- Come sarà possibile modificare parti di software nell'ambiente di produzione con tempi di inattività minimi?

- Come sarà possibile adattare in scala gli ambienti e monitorare il sistema di produzione?

- Come includere il test e la distribuzione di contenitori nella pipeline di versione?

- Come usare strumenti/piattaforme open source per i contenitori in Microsoft Azure?

Se si è in grado di rispondere a tutte queste domande, vale la pena considerare la possibilità di spostare le applicazioni in uso (nuove o esistenti) nei contenitori Docker.

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a>Introduzione a un flusso di lavoro del ciclo di vita di applicazione Docker end-to-end generica

La figura 2-2 presenta un flusso di lavoro più dettagliato per il ciclo di vita di un'applicazione Docker. In questa istanza vengono evidenziati asset e attività DevOps specifici.

![Diagramma che mostra il ciclo di vita end-to-end generico di un'app Docker.](./media/containers-foundation-for-devops-collaboration/generic-end-to-enddpcker-app-life-cycle.png)

**Come illustrato 2-2.** Flusso di lavoro generale per il ciclo di vita dell'applicazione in contenitori Docker

Tutto inizia con lo sviluppatore, che inizia a creare codice per il flusso di lavoro del ciclo interno. La fase del ciclo interno è quella in cui gli sviluppatori definiscono tutto ciò che accade prima del push del codice nel repository di codice (ad esempio un sistema di controllo del codice sorgente come Git). Dopo il commit, il repository attiva l'integrazione continua (CI) e il resto del flusso di lavoro.

Il ciclo interno è costituito essenzialmente da passaggi tipici, ad esempio "creazione di codice", "esecuzione", "test" e "debug" e dai passaggi aggiuntivi necessari immediatamente prima dell'esecuzione dell'app in locale. Questo è il processo usato dallo sviluppatore per eseguire e sottoporre a test l'app come contenitore Docker. Il flusso di lavoro del ciclo interno viene descritto nelle sezioni che seguono.

Se si torna a esaminare il flusso di lavoro end-to-end si noterà che il flusso di lavoro di DevOps è più di una tecnologia o un set di strumenti: è un approccio che richiede un'evoluzione a livello di implementazione. È costituito dalle persone, dai processi e dagli strumenti appropriati per rendere il ciclo di vita dell'applicazione più veloce e più prevedibile. In genere, le aziende che adottano un flusso di lavoro in contenitori ristrutturano le proprie organizzazioni per rappresentare le persone e i processi che corrispondono al flusso di lavoro in contenitori.

L'adozione di DevOps può aiutare i team a rispondere insieme e più velocemente alle pressioni competitive, implementando l'automazione per sostituire processi manuali soggetti a errori e di conseguenza migliorando la tracciabilità e adottando flussi di lavoro ripetibili. Le organizzazioni possono anche gestire gli ambienti in modo più efficiente e realizzare risparmi sui costi grazie a una combinazione di risorse cloud e locali e a set di strumenti integrati.

Quando si implementa il flusso di lavoro DevOps per le applicazioni Docker, si noterà che le tecnologie Docker sono presenti in quasi tutte le fasi del flusso di lavoro, dalla casella di sviluppo durante l'uso nel ciclo interno (creazione di codice, esecuzione, debug) alla fase di compilazione-test-integrazione continua, fino alla distribuzione dei contenitori agli ambienti di staging e produzione.

Il miglioramento delle procedure di qualità aiuta a identificare i difetti nelle prime fasi del ciclo di sviluppo e a ridurre i costi di correzione degli errori. Grazie all'inclusione dell'ambiente e delle dipendenze nell'immagine e all'adozione dell'approccio che prevede la distribuzione della stessa immagine in più ambienti, si promuove la pratica di estrazione delle configurazioni specifiche per l'ambiente, rendendo più affidabili le distribuzioni.

I dati completi ottenuti tramite strumenti efficaci (monitoraggio e diagnostica) consentono l'analisi approfondita dei problemi di prestazioni e del comportamento degli utenti, per orientare le priorità e gli investimenti futuri.

DevOps deve essere considerato come un viaggio, non come una destinazione. L'approccio va implementato in modo incrementale tramite progetti con ambiti appropriati, da cui è possibile ottenere risultati positivi e favorire l'apprendimento e l'evoluzione.

## <a name="benefits-of-devops-for-containerized-applications"></a>Vantaggi di DevOps per le applicazioni in contenitori

Ecco alcuni dei vantaggi più importanti offerti da un flusso di lavoro DevOps consolidato:

- Distribuire software di miglior qualità, più velocemente e con conformità migliore.

- Promuovere il miglioramento continuo e le rettifiche con maggior tempestività e riduzione dei costi.

- Aumentare la trasparenza e la collaborazione tra gli stakeholder coinvolti nella distribuzione e nella gestione del software.

- Controllare i costi e usare le risorse di provisioning in modo più efficace, riducendo al minimo i rischi per la sicurezza.

- Garantire un'integrazione plug-and-play ottimale con molti investimenti in DevOps già implementati, inclusi gli investimenti nell'ambiente open source.

>[!div class="step-by-step"]
>[Successivo](index.md)
>[precedente](../Microsoft-platform-tools-containerized-apps/index.md)
