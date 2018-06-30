---
title: Contenitori come base per la collaborazione DevOps
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 6c7de61f421cf2c45cd3c5ee9afc5a388e985b52
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105563"
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a>Contenitori come base per la collaborazione DevOps

Per la natura dei contenitori e delle tecnologie di Docker, gli sviluppatori possono condividere software e le dipendenze facilmente con le operazioni IT e gli ambienti di produzione eliminando il tipico scuse "funziona nel computer". I contenitori di risolvere i conflitti di applicazione tra ambienti diversi. Indirettamente, i contenitori e Docker riunire gli sviluppatori e gli operatori IT più vicino, rendendo più semplice per loro di collaborare in modo efficace. Adottare il flusso di lavoro contenitore fornisce molti clienti che con la continuità DevOps aver ricercato ma in precedenza era necessario implementare tramite configurazione più complessa per il rilascio e compilare le pipeline. I contenitori di semplificano le pipeline di compilazione/test/distribuzione in DevOps.

![](./media/image1.png)

Figura 2-1: i carichi di lavoro principale per "persone"dedite"del ciclo di vita per le applicazioni nei contenitori di Docker

Con contenitori di Docker, gli sviluppatori propri che cos'è all'interno del contenitore (applicazione e servizio e le dipendenze di Framework e componenti) e i contenitori e i servizi comportano insieme come un'applicazione composta da una raccolta di servizi. Interdipendenze di più contenitori vengono definite in un file docker compose.yml o ciò che potrebbe essere chiamato una *manifesto della distribuzione*. Nel frattempo, i team operativi IT (i professionisti IT e gestione) possono concentrarsi sulla gestione degli ambienti di produzione; infrastruttura; scalabilità; monitoraggio; e, infine, assicurandosi che le applicazioni forniscono in modo corretto per gli utenti finali, senza dover conoscere il contenuto dei contenitori diversi. Di conseguenza, il nome "contenitore," richiamo analogia ai contenitori di spedizione del mondo reale. Di conseguenza, i proprietari del contenuto del contenitore necessitano non riguardano autonomamente con modo in cui verrà inviato il contenitore e i trasporti aziendale shipping un contenitore dal suo punto di origine alla destinazione senza conoscere o caring al relativo contenuto. In modo analogo, gli sviluppatori possono creare e possedere il contenuto all'interno di un contenitore Docker senza la necessità di occuparsi i meccanismi di "transport".

Pillar sul lato sinistro della figura 2-1, gli sviluppatori di scrivere, eseguire codice in locale nei contenitori Docker usando Docker per Windows o Mac. Definiscono l'ambiente operativo per il codice usando un Dockerfile che specifica il sistema operativo di base per l'esecuzione, nonché i passaggi di compilazione per compilare il codice in un'immagine di Docker. Gli sviluppatori di definiscono una o più immagini verranno interazione tramite citato *docker compose.yml* file manifesto di distribuzione. Quando vengono completate lo sviluppo locale, codice dell'applicazione oltre ai file di configurazione di Docker sono push nel repository di codice di propria scelta (vale a dire, archivio Git).

L'elemento chiave DevOps definisce le pipeline di compilazione – Continuous Integration (CI) usando il Dockerfile fornito nel repository di codice. Il sistema CI estrae le immagini contenitore di base dal Registro di sistema Docker selezionato e crea le immagini Docker personalizzate per l'applicazione. Le immagini quindi vengono convalidate e inserite nel Registro di sistema di Docker utilizzati per le distribuzioni in più ambienti.

In pillar sulla destra, operazioni di gestire i team distribuiti applicazioni e dell'infrastruttura nell'ambiente di produzione durante il monitoraggio l'ambiente e le applicazioni in modo che possano fornire commenti e suggerimenti e informazioni dettagliate per il team di sviluppo sul modo in cui l'applicazione potrebbe essere migliorate. App contenitore vengono in genere eseguite nell'ambiente di produzione usando orchestrators contenitore.

I due team collaborano tramite una piattaforma fondamentale (Docker containers) che fornisce una separazione delle problematiche come un contratto, migliorando notevolmente collaborazione i due team nel ciclo di vita dell'applicazione. Gli sviluppatori proprietari i contenuti del contenitore, il relativo ambiente operativo e le interdipendenze del contenitore, mentre i team operativi accettano le immagini compilate insieme il manifesto e li esegue del proprio sistema di orchestrazione.

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a>Introduzione a un generico end-to-end Docker applicazione ciclo di vita del flusso di lavoro

Figura 2-2 presenta un flusso di lavoro più dettagliato per un ciclo di vita dell'applicazione di Docker, con particolare attenzione in questa istanza agli asset e specifiche attività DevOps.

![](./media/image2.png)

Figura 2-2: flusso di lavoro generale per il ciclo di vita dell'applicazione nei contenitori di Docker

Tutto ciò che inizia con lo sviluppatore che ha avviato la scrittura di codice nel flusso di lavoro ciclo interno. La fase del ciclo interno è in cui gli sviluppatori di definiscono tutti gli elementi che si verifica prima il push di codice al repository di codice (ad esempio, un sistema di controllo origine, ad esempio Git). Dopo aver eseguito il commit, il repository Attiva integrazione continua (CI) e il resto del flusso di lavoro.

Il ciclo interno è essenzialmente costituita da passaggi tipici, ad esempio "code", "run", "test" e "debug", più passaggi aggiuntivi direttamente prima di eseguire l'app localmente. Si tratta quando lo sviluppatore esegue e controlla l'app come un contenitore Docker. Il flusso di lavoro ciclo interno verrà illustrato nelle sezioni che seguono.

Eseguire un nuovo per esaminare il end-to-end del flusso di lavoro, il flusso di lavoro DevOps è maggiore rispetto a una tecnologia o un set di strumenti: si tratta di un modello mentale che richiede l'evoluzione relative alla lingua. È persone, processi e gli strumenti appropriati per rendere il ciclo di vita dell'applicazione più veloce e più prevedibile. Le aziende che adottano in genere un flusso di lavoro nei contenitori ristrutturare delle organizzazioni per rappresentare gli utenti e i processi che soddisfano il flusso di lavoro nei contenitori.

Esercitazione DevOps consente a team rispondono più velocemente insieme le pressioni della concorrenza di sostituendo processi manuali soggetti a errori con l'automazione, determinando la tracciabilità migliorata e ripetibile flussi di lavoro. Le organizzazioni può anche gestire gli ambienti in modo più efficiente e realizzare risparmi con una combinazione di risorse cloud e locali, nonché gli strumenti perfettamente integrati.

Quando si implementa il flusso di lavoro DevOps per le applicazioni di Docker, si noterà che sono presenti in quasi tutte le fasi del flusso di lavoro, da una finestra di sviluppo mentre si lavora nel ciclo interno (codice, eseguire, debug), per la fase di compilazione-test-elementi di configurazione, le tecnologie di Docker e, Naturalmente, nel server di produzione e ambienti di gestione temporanea e durante la distribuzione ai contenitori in questi ambienti.

Miglioramento delle procedure consigliate di qualità aiuta a identificare i difetti del ciclo di sviluppo, riducendo così il costo di correggerli. Tra cui l'ambiente e le dipendenze nell'immagine e adottando una filosofia di distribuzione l'immagine stessa tra più ambienti, si innalza di livello una disciplina di estrarre le configurazioni specifiche dell'ambiente effettuare distribuzioni più affidabile.

Dati complessi ottenuti tramite la strumentazione efficace (monitoraggio e diagnostica) offre una visione problemi di prestazioni e il comportamento di utente per guidare gli investimenti e le priorità future.

DevOps deve essere considerato un viaggio, non una destinazione. E deve essere implementato in modo incrementale per i progetti in modo appropriato con ambiti da cui è possibile illustrare esito positivo, informazioni ed evolvere.

## <a name="benefits-of-devops-for-containerized-applications"></a>Vantaggi di DevOps per le applicazioni nei contenitori

Ecco alcuni dei vantaggi più importanti forniti da un flusso di lavoro DevOps a tinta unita:

-   Rilasciare il software di qualità superiore, più velocemente e con maggiore conformità

-   Favorire le regolazioni e il miglioramento continuo versioni precedenti e più economica

-   Aumentare la trasparenza e la collaborazione tra le parti interessate coinvolte nella distribuzione e il funzionamento del software

-   Controllare i costi e utilizzano le risorse di provisioning in modo più efficace riducendo al minimo i rischi di sicurezza

-   Plug and play bene con molti degli investimenti DevOps esistenti, tra cui gli investimenti in open source di

>[!div class="step-by-step"]
[Precedente](index.md)
[Successivo](../Microsoft-platform-tools-containerized-apps/index.md)
