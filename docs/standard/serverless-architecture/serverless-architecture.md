---
title: Architettura senza server - App senza server
description: Esplorazione delle varie architetture e le app supportate da architetture senza server, tra cui App web, mobili e IoT.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 60d225d9794d5c15b0cd8e42800ccad4d7872756
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904787"
---
# <a name="serverless-architecture"></a>Architettura senza server

Esistono molti approcci per l'utilizzo [senza server](http://azure.com/serverless) architetture. In questo capitolo illustra esempi di architetture comuni che si integrano senza server. Vengono inoltre descritti i problemi che possono comportare problemi aggiuntivi o richiedono attenzione aggiuntiva durante l'implementazione senza server. Infine, alcuni esempi di progettazione vengono forniti che illustrano diversi casi d'uso senza server.

Host senza server usano spesso un esistente basato su contenitori o un livello PaaS per gestire le istanze senza server. Ad esempio, funzioni di Azure si basa sul [servizio App di Azure](https://docs.microsoft.com/azure/app-service/). Il servizio App consente di aumentare le istanze e gestire il runtime che esegue il codice di funzioni di Azure. Per le funzioni basate su Windows, viene eseguito l'host come PaaS e delle scale out il runtime di .NET. Per le funzioni basate su Linux, l'host si basa su contenitori.

![Architettura di funzioni di Azure](./media/azure-functions-architecture.png)

Il nucleo di processi Web fornisce un contesto di esecuzione per la funzione. Il Runtime di linguaggio esegue gli script, esegue le librerie e ospita il framework per la lingua di destinazione. Ad esempio, Node. js viene usato per eseguire funzioni JavaScript e .NET Framework viene usato per eseguire le funzioni c#. Si apprenderà ulteriori informazioni sulle opzioni di linguaggio e piattaforma più avanti in questo capitolo.

Alcuni progetti possono trarre vantaggio da un "secondo" per approccio senza server. Le applicazioni che si basano su microservizi possono implementare tutti i microservizi tramite la tecnologia senza server. La maggior parte delle App sono ibrido, seguendo una progettazione a più livelli e l'uso senza server per i componenti che hanno un significato perché i componenti sono modulare e scalabile in modo indipendente. Per consentire questi scenari ha senso, questa sezione illustra alcuni esempi comuni di architettura che usano senza server.

## <a name="full-serverless-back-end"></a>Full senza server back-end

Il back-end completo senza server è ideale per diversi tipi di scenari, in particolare durante la compilazione di nuove o le applicazioni "vergine". Un'applicazione con una vasta area della superficie di API può trarre vantaggio dall'implementazione di ogni API come una funzione senza server. Le app che si basano sull'architettura di microservizi sono un altro esempio che può essere implementato come un back-end completo senza server. I microservizi comunicano su protocolli diversi tra loro. Gli scenari specifici includono:

* Prodotti SaaS basato su API (esempio: processore pagamenti finanziari).
* Le applicazioni basate su messaggi (esempio: soluzione di monitoraggio dei dispositivi).
* Le app incentrata sull'integrazione tra i servizi (esempio: applicazione di prenotazione delle compagnie aeree).
* Processi in esecuzione periodica (esempio: pulizia del database basato su timer).
* Le app con stato attivo sulla trasformazione dei dati (esempio: importazione attivata dal caricamento di file).
* Estrarre i processi di trasformazione e caricamento (ETL).

Esistono casi d'uso più specifici che vengono analizzati più avanti in questo documento.

## <a name="monoliths-and-starving-the-beast"></a>Strutture monolitiche e "sottrarre il beast"

Un problema comune è la migrazione di un'applicazione monolitica esistente nel cloud. L'approccio meno rischioso è "lift- and -shift" interamente in macchine virtuali. Molti negozi preferiscono usare la migrazione come un'opportunità per modernizzare la propria base di codice. Un pratico approccio alla migrazione viene chiamato "starvation il beast". In questo scenario il monolite viene eseguita la migrazione "così com'è" per iniziare. Quindi, sono modernizzati servizi selezionati. In alcuni casi, la firma del servizio è identica all'originale: è sufficiente ospitato come una funzione. I client vengono aggiornati per usare il nuovo servizio anziché l'endpoint di App monolitica. Nel frattempo, i passaggi, ad esempio la replica di database abilitano microservizi ospitare i propri archiviazione anche quando le transazioni sono comunque gestite dall'App monolitica. Infine, tutti i client verranno eseguita la migrazione dei nuovi servizi. Il monolite "risentirne" (i servizi non è più denominati) fino a quando tutte le funzionalità sono stata sostituita. La combinazione degli strumenti senza server e i proxy possono facilitare la gran parte della migrazione.

![Migrazione di un monolito senza server](./media/serverless-monolith-migration.png)

Per altre informazioni su questo approccio, guardare il video: [Crea la tua app nel cloud con funzioni di Azure senza server](https://channel9.msdn.com/Events/Connect/2017/E102).

## <a name="web-apps"></a>App Web

Le app Web sono ottimi candidati per le applicazioni senza server. Esistono due approcci comuni per le app web oggi stesso: basato su server e basato su client (ad esempio, applicazione a pagina singola o applicazione a singola pagina). Le app web basate su server usano in genere un livello del middleware per eseguire chiamate API per eseguire il rendering dell'interfaccia utente web. Le applicazioni SPA di effettuare chiamate API REST direttamente dal browser. In entrambi gli scenari senza server possono contenere il middleware o la richiesta di API REST, fornendo la logica di business necessaria. Un'architettura comune è realizzare un server web leggero statico. L'applicazione di pagina singola (SPA) serve HTML, CSS, JavaScript e altri asset di browser. L'app web si connette quindi a microservizi back-end.

## <a name="mobile-back-ends"></a>Back-end mobili

Il paradigma delle App senza server basata su eventi rende ideale come back-end per dispositivi mobili. Il dispositivo mobile attiva gli eventi e viene eseguito il codice senza server per soddisfare le richieste. Sfruttando i vantaggi di un modello senza server consente agli sviluppatori di migliorare la logica di business senza che sia necessario distribuire un aggiornamento completo dell'applicazione. L'approccio senza server consente inoltre ai team di condividere gli endpoint e operare in parallelo.

Gli sviluppatori per dispositivi mobili possono compilare una logica di business senza diventare esperti sul lato server. In genere, le App per dispositivi mobili connessi ai servizi locali. Il livello di servizio di compilazione necessarie informazioni sulla piattaforma server e paradigma di programmazione. Gli sviluppatori ha collaborato con operazioni per il provisioning di server e configurarli in modo appropriato. In alcuni casi giorni o anche settimane impiegati nella creazione di una pipeline di distribuzione. Tutti questi problemi vengono risolti da senza server.

Serverless astrae le dipendenze sul lato server e consente allo sviluppatore di concentrarsi sulla logica di business. Ad esempio, uno sviluppatore per dispositivi mobili che compila le app usano un framework JavaScript possa compilare anche le funzioni senza server con JavaScript. L'host senza server gestisce il sistema operativo, un'istanza di Node. js per ospitare il codice, le dipendenze dei pacchetti e altro ancora. Lo sviluppatore viene fornito un semplice set di input e un modello standard per gli output. È quindi possibile concentrarsi sulla compilazione e test la logica di business. Di conseguenza gli utenti possono usare le competenze esistenti per compilare la logica di back-end per l'app per dispositivi mobili senza dover apprendere nuove piattaforme o diventa uno "sviluppatore per sul lato server".

![Terminare nuovamente per dispositivi mobili senza server](./media/serverless-mobile-backend.png)

La maggior parte dei provider di servizi cloud offrono prodotti senza server basata su dispositivi mobili che consentono di semplificare il ciclo di vita di sviluppo per dispositivi mobili intero. I prodotti possono automatizzare il provisioning dei database per rendere persistenti i dati, gestire problemi di DevOps, fornire basato sul cloud si basa e i Framework e la possibilità di processi di business di script con lo sviluppatore di test la lingua preferita. Seguendo un approccio incentrato sui dispositivi mobili senza server, è possibile semplificare il processo. Serverless rimuove il sovraccarico enorme di provisioning, configurazione e gestione dei server per il back-end per dispositivi mobili.

## <a name="internet-of-things-iot"></a>Internet delle cose (IoT)

IoT fa riferimento agli oggetti fisici collegati in rete. Vengono talvolta definite come "dispositivi connessi" o "smart Device." Tutti i dati da automobili e distributori possono essere collegati e inviare dati che vanno dall'inventario per i dati del sensore, ad esempio temperatura e umidità. Nell'organizzazione, IoT ti offre i miglioramenti ai processi di business attraverso il monitoraggio e automazione. I dati IoT consente di regolare il clima in un data warehouse di grandi dimensioni o tenere traccia dell'inventario attraverso la catena di fornitura. IoT può rilevare spill chimiche e chiamare il vigili del fuoco quando viene rilevato fumo.

Il volume di dispositivi e le informazioni spesso determina un'architettura guidata dagli eventi alla route ed elaborare messaggi. Senza server è una soluzione ideale per diversi motivi:

* Abilita la scalabilità del volume di dati e dispositivi aumenta.
* Supporta l'aggiunta di nuovi endpoint per supportare nuovi dispositivi e sensori.
* Facilita il controllo delle versioni indipendente in modo che gli sviluppatori possono aggiornare la logica di business per un dispositivo specifico senza dover distribuire l'intero sistema.
* Resilienza e tempi di inattività inferiori.

La diffusione di Internet delle cose ha comportato diversi prodotti senza server che si occupano di problemi di IoT, in particolare, ad esempio [IoT Hub di Azure](https://docs.microsoft.com/azure/iot-hub). Le attività come registrazione del dispositivo, applicazione dei criteri, rilevamento e anche la distribuzione di codice per i dispositivi a automatizzate Serverless *bordo*. Il bordo fa riferimento ai dispositivi, ad esempio i sensori e attuatori connessi a, ma non una parte attiva del, Internet.

>[!div class="step-by-step"]
>[Precedente](architecture-approaches.md)
>[Successivo](serverless-architecture-considerations.md)
