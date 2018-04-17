---
title: Contenitori come base per la collaborazione DevOps
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f7d0f9b1d72f353b2c22f846f723c82f769f6a4e
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a>Contenitori come base per la collaborazione DevOps

Per natura dei contenitori e delle tecnologie di Docker, gli sviluppatori possono condividere software e le dipendenze facilmente con gli ambienti di produzione e gli operatori IT eliminando il tipico scuse "funziona nel computer". Contenitori di risolvere i conflitti di applicazione tra ambienti diversi. Indirettamente, contenitori e Docker riunire gli sviluppatori e le operazioni IT più vicino, rendendo più semplice per loro di collaborare in modo efficace. Adottare il flusso di lavoro contenitore fornisce molti clienti con la continuità DevOps aver ricercato ma in precedenza era necessario implementare tramite la configurazione più complessa per il rilascio e compilare le pipeline. Contenitori di semplificano le pipeline di compilazione/test/distribuzione in DevOps.

![](./media/image1.png)

Figura 2-1: i carichi di lavoro principale per gli utenti "tipo" del ciclo di vita per le applicazioni nei contenitori di Docker

Con i contenitori di Docker, gli sviluppatori propri che cos'è all'interno del contenitore (applicazione e servizio e le dipendenze di Framework e componenti) e i contenitori e i servizi comportano insieme come un'applicazione composta da una raccolta di servizi. Interdipendenze di più contenitori vengono definite in un file docker compose.yml o ciò che potrebbe essere chiamato una *manifesto di distribuzione*. Nel frattempo, i team operativi IT (i professionisti IT e gestione) possono concentrarsi sulla gestione degli ambienti di produzione; infrastruttura; scalabilità; monitoraggio; e, infine, assicurandosi che le applicazioni forniscono in modo corretto per gli utenti finali, senza dover conoscere il contenuto dei contenitori diversi. Di conseguenza, il nome "contenitore," richiamo l'analogia ai contenitori di spedizione del mondo reale. Di conseguenza, i proprietari del contenuto di un contenitore necessitano non riguardano con modalità verrà inviato il contenitore e i trasporti società di spedizione un contenitore dal suo punto di origine alla destinazione senza conoscere o caring al relativo contenuto. In modo analogo, gli sviluppatori possono creare e proprietari di contenuto all'interno di un contenitore Docker senza la necessità di occuparsi i meccanismi di "trasporto".

Pillar sul lato sinistro della figura 2-1, gli sviluppatori di scrivere, eseguire codice in locale in contenitori di Docker tramite Docker per Windows o Mac. Definiscono l'ambiente operativo per il codice usando un Dockerfile che specifica il sistema operativo di base per l'esecuzione, nonché i passaggi di compilazione per compilare il codice in un'immagine di Docker. Gli sviluppatori di definiscono come le immagini di uno o più verranno interagiscono tramite il suddetto *docker compose.yml* file manifesto di distribuzione. Quando vengono completate lo sviluppo locale, codice dell'applicazione e i file di configurazione di Docker sono push nel repository di codice di propria scelta (vale a dire il repository Git).

L'elemento chiave DevOps definisce le pipeline di compilazione – Continuous integrazione (CI) usando il Dockerfile fornito nel repository di codice. Il sistema CI le immagini contenitore di base dal Registro di sistema Docker selezionato e compila immagini Docker personalizzate per l'applicazione. Le immagini vengono quindi convalidate e inserite nel Registro di sistema di Docker utilizzati per le distribuzioni in più ambienti.

In pillar a destra, le operazioni di gestire i team distribuiti applicazioni e dell'infrastruttura nell'ambiente di produzione durante il monitoraggio di ambiente e alle applicazioni in modo che possano fornire commenti e suggerimenti e informazioni dettagliate per il team di sviluppo sulle modalità con cui l'applicazione potrebbe essere migliorate. App contenitore vengono in genere eseguite nell'ambiente di produzione utilizzando orchestrators contenitore.

I due team collaborano tramite una piattaforma di base (contenitori Docker) che fornisce una separazione delle problematiche come un contratto, migliorando notevolmente collaborazione i due team nel ciclo di vita dell'applicazione. Gli sviluppatori proprietari i contenuti del contenitore, l'ambiente operativo e le interdipendenze del contenitore, mentre i team operativi rendere le immagini insieme il manifesto incorporate e li esegue nel sistema di orchestrazione.

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a>Introduzione a un generico end-to-end Docker applicazione ciclo di vita del flusso di lavoro

Figura 2-2 presenta un flusso di lavoro più dettagliata per un ciclo di vita dell'applicazione di Docker, porre l'attenzione su attività e attività specifiche di DevOps in questa istanza.

![](./media/image2.png)

Figura 2-2: flusso di lavoro generale per il ciclo di vita delle applicazioni nei contenitori Docker

Tutto ciò che inizia con lo sviluppatore che ha avviato la scrittura di codice nel ciclo interno flusso di lavoro. La fase del ciclo interno è in cui gli sviluppatori di definiscono tutti gli elementi che si verifica prima dell'inserimento di codice al repository di codice (ad esempio, un sistema di controllo origine, ad esempio Git). Dopo aver eseguito il commit, il repository Attiva integrazione continua (CI) e il resto del flusso di lavoro.

Il ciclo interno è essenzialmente costituita da passaggi tipici come "codice", "run", "test" e "debug", più passaggi aggiuntivi direttamente prima di eseguire l'app localmente. Si tratta quando lo sviluppatore è in esecuzione e test dell'app come un contenitore Docker. Il flusso di lavoro interna ciclo verrà spiegato nelle sezioni che seguono.

Riprendendo un passaggio per esaminare il end-to-end del flusso di lavoro, il flusso di lavoro DevOps è maggiore rispetto a una tecnologia o un set di strumenti: si tratta di un modello mentale che richiede l'evoluzione relative alla lingua. È persone, processi e gli strumenti appropriati per rendere il ciclo di vita dell'applicazione più veloce e più prevedibile. Le aziende che adottano in genere un flusso di lavoro nei contenitori ristrutturare delle organizzazioni per rappresentare gli utenti e i processi che corrispondono al flusso di lavoro nei contenitori.

Esercitazione DevOps consente a team rispondono più velocemente insieme le pressioni di concorrenza di sostituendo i processi manuali soggetti a errori con l'automazione, con conseguente miglioramento della tracciabilità e ripetibile flussi di lavoro. Le organizzazioni possono anche gestire gli ambienti in modo più efficiente e realizzare risparmi sui costi con una combinazione di risorse cloud e locali, nonché gli strumenti integrati.

Quando si implementa il flusso di lavoro DevOps per le applicazioni di Docker, si noterà che le tecnologie di Docker sono presenti in quasi tutte le fasi del flusso di lavoro, dalla casella di sviluppo durante l'utilizzo nel ciclo interno (codice, eseguire, debug), per la fase di compilazione-test-CI e, Naturalmente, di produzione e di ambienti di gestione temporanea e durante la distribuzione ai contenitori in tali ambienti.

Miglioramento delle procedure consigliate di qualità consente di identificare i difetti del ciclo di sviluppo, che consente di ridurre il costo di correggerli. Includendo l'ambiente e le dipendenze nell'immagine e adottare degli scopi di distribuzione dell'immagine stessa in ambienti diversi, si innalza di livello una disciplina di estrarre le configurazioni specifiche dell'ambiente eseguendo le distribuzioni più affidabile.

Dati dettagliati tramiti strumentazione efficace (monitoraggio e diagnostica) forniscono informazioni approfondite problemi di prestazioni e il comportamento di utente per gestire gli investimenti e le future priorità.

DevOps deve essere considerato un viaggio, non è una destinazione. E deve essere implementato in modo incrementale per i progetti in modo appropriato con ambiti da cui è possibile illustrare esito positivo, informazioni ed evolvere.

## <a name="benefits-of-devops-for-containerized-applications"></a>Vantaggi di DevOps per le applicazioni nei contenitori

Ecco alcuni dei vantaggi più importanti forniti da un flusso di lavoro DevOps a tinta unita:

-   Distribuire il software di qualità superiore, più rapidamente e con maggiore conformità

-   Unità di modifiche e il miglioramento continuo versioni precedenti e più economica

-   Aumentare la trasparenza e la collaborazione tra le parti interessate coinvolte nella distribuzione e del software

-   Controllare i costi e utilizzano le risorse di provisioning in modo più efficace, riducendo al minimo i rischi di sicurezza

-   Plug and play bene con molti degli investimenti DevOps esistenti, inclusi gli investimenti in open source di

>[!div class="step-by-step"]
[Precedente] (index.md) [Avanti] (... /Microsoft-Platform-Tools-containerized-Apps/index.MD)
