---
title: Architettura senza server-app senza server
description: Esplorazione di varie architetture e app supportate da architetture senza server, tra cui app Web, dispositivi mobili e Internet.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 3b22fecfdc693154dbdeb3e872e0e246e8ca41f9
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577354"
---
# <a name="serverless-architecture"></a>Architettura serverless

Sono disponibili molti approcci per l'utilizzo di architetture senza [Server](https://azure.com/serverless) . In questo capitolo vengono esaminati esempi di architetture comuni che integrano senza server. Vengono inoltre illustrate le problematiche che possono comportare ulteriori problemi o che richiedono considerazioni aggiuntive quando si implementano senza server. Infine, vengono forniti diversi esempi di progettazione che illustrano diversi casi d'uso senza server.

Gli host senza server spesso utilizzano un livello basato su contenitore o PaaS esistente per gestire le istanze senza server. Ad esempio, funzioni di Azure si basa sul [servizio app Azure](https://docs.microsoft.com/azure/app-service/). Il servizio app viene usato per scalare le istanze e gestire il runtime che esegue il codice di funzioni di Azure. Per le funzioni basate su Windows, l'host viene eseguito come PaaS e scala in orizzontale il Runtime .NET. Per le funzioni basate su Linux, l'host sfrutta i contenitori.

![Architettura di funzioni di Azure](./media/azure-functions-architecture.png)

Il nucleo di processi Web fornisce un contesto di esecuzione per la funzione. Il runtime del linguaggio esegue gli script, esegue le librerie e ospita il Framework per la lingua di destinazione. Node. js, ad esempio, viene usato per eseguire funzioni JavaScript e il .NET Framework viene usato per C# eseguire le funzioni. Verranno fornite ulteriori informazioni sulle opzioni relative alla lingua e alla piattaforma più avanti in questo capitolo.

Alcuni progetti possono trarre vantaggio dall'adozione di un approccio "All-in" a senza server. Le applicazioni che si basano molto sui microservizi possono implementare tutti i microservizi usando la tecnologia senza server. La maggior parte delle app è ibrida, seguendo una progettazione a più livelli e usando senza server per i componenti che hanno senso perché i componenti sono modulari e scalabili in modo indipendente. Per avere un'idea di questi scenari, in questa sezione vengono illustrati alcuni esempi di architettura comuni che utilizzano senza server.

## <a name="full-serverless-back-end"></a>Back-end senza server completo

Il back-end senza server completo è ideale per diversi tipi di scenari, soprattutto quando si compilano applicazioni nuove o "verdi". Un'applicazione con una grande superficie di attacco API può trarre vantaggio dall'implementazione di ogni API come funzione senza server. Le app basate sull'architettura di microservizi sono un altro esempio che può essere implementato come back-end senza server completo. I microservizi comunicano su diversi protocolli tra loro. Gli scenari specifici includono:

* Prodotti SaaS basati su API (ad esempio, elaborazione di pagamenti finanziari).
* Applicazioni basate su messaggi (esempio: soluzione di monitoraggio dei dispositivi).
* App incentrate sull'integrazione tra i servizi, ad esempio l'applicazione di prenotazione aerea.
* Processi eseguiti periodicamente, ad esempio la pulizia del database basata su timer.
* App incentrate sulla trasformazione dei dati (esempio: importazione attivata dal caricamento di file).
* Estrae processi ETL (Transform and Load).

Ci sono altri casi d'uso più specifici descritti più avanti in questo documento.

## <a name="monoliths-and-starving-the-beast"></a>Monolitici e "fame bestia"

Un problema comune è la migrazione di un'applicazione monolitica esistente al cloud. L'approccio meno rischioso è quello di "Lift-and-Shift" interamente su macchine virtuali. Molti negozi preferiscono usare la migrazione come opportunità per modernizzare la base di codice. Un approccio pratico alla migrazione è denominato "fame della bestia". In questo scenario, il monolito viene migrato "così com'è" per iniziare con. Quindi, i servizi selezionati vengono modernizzati. In alcuni casi, la firma del servizio è identica a quella originale: è semplicemente ospitata come funzione. I client vengono aggiornati per usare il nuovo servizio anziché l'endpoint monolitico. Nel frattempo, i passaggi, ad esempio la replica di database, consentono ai microservizi di ospitare la propria archiviazione anche quando le transazioni sono ancora gestite da Monolith. Infine, viene eseguita la migrazione di tutti i client sui nuovi servizi. Il monolito è "affamato" (i servizi non vengono più chiamati) finché tutte le funzionalità non sono state sostituite. La combinazione di proxy e senza server può facilitare gran parte della migrazione.

![Migrazione di Monolith senza server](./media/serverless-monolith-migration.png)

Per ulteriori informazioni su questo approccio, guardare il video: [Porta la tua app nel cloud con funzioni di Azure senza server](https://channel9.msdn.com/Events/Connect/2017/E102).

## <a name="web-apps"></a>App Web

Le app Web sono ottime candidate per le applicazioni senza server. Attualmente esistono due approcci comuni alle app Web: basati su server e basati su client, ad esempio applicazione a pagina singola o SPA. Le app Web basate su server usano in genere un livello middleware per emettere chiamate API per eseguire il rendering dell'interfaccia utente Web. Le applicazioni SPA effettuano chiamate API REST direttamente dal browser. In entrambi gli scenari, senza server è possibile supportare il middleware o la richiesta dell'API REST fornendo la logica di business necessaria. Un'architettura comune è costituita da un server Web statico leggero. L'applicazione a pagina singola (SPA) serve HTML, CSS, JavaScript e altri asset del browser. L'app Web si connette quindi a un back-end di microservizi.

## <a name="mobile-back-ends"></a>Back-end per dispositivi mobili

Il paradigma basato sugli eventi di app senza server li rende ideali come back-end per dispositivi mobili. Il dispositivo mobile attiva gli eventi e il codice senza server viene eseguito per soddisfare le richieste. Sfruttare i vantaggi di un modello senza server consente agli sviluppatori di migliorare la logica di business senza dover distribuire un aggiornamento completo dell'applicazione. L'approccio senza server consente inoltre ai team di condividere gli endpoint e lavorare in parallelo.

Gli sviluppatori di dispositivi mobili possono compilare la logica di business senza diventare esperti sul lato server. Tradizionalmente, le app per dispositivi mobili sono connesse ai servizi locali. Compilazione del livello di servizio necessario per comprendere la piattaforma server e il paradigma di programmazione. Gli sviluppatori hanno lavorato con operazioni per eseguire il provisioning dei server e configurarli in modo appropriato In alcuni giorni o addirittura settimane è stato impiegato per la creazione di una pipeline di distribuzione. Tutti questi problemi vengono risolti da server.

Senza server astrae le dipendenze lato server e consente allo sviluppatore di concentrarsi sulla logica di business. Ad esempio, uno sviluppatore di dispositivi mobili che compila app usando un framework JavaScript può anche creare funzioni senza server con JavaScript. L'host senza server gestisce il sistema operativo, un'istanza di node. js per ospitare il codice, le dipendenze del pacchetto e altro ancora. Lo sviluppatore fornisce un semplice set di input e un modello standard per gli output. Possono quindi concentrarsi sulla compilazione e sul test della logica di business. Sono quindi in grado di usare le competenze esistenti per creare la logica back-end per l'app per dispositivi mobili senza dover apprendere nuove piattaforme o diventare uno "sviluppatore lato server".

![Back-end mobile senza server](./media/serverless-mobile-backend.png)

La maggior parte dei provider di servizi cloud offre prodotti senza server basati su dispositivi mobili che semplificano l'intero ciclo di vita di sviluppo I prodotti possono automatizzare il provisioning dei database per rendere permanente i dati, gestire i problemi relativi a DevOps, fornire Framework di test e compilazioni basati sul cloud e la possibilità di creare script per processi di business usando il linguaggio preferito dello sviluppatore. Seguendo un approccio senza server incentrato sui dispositivi mobili è possibile semplificare il processo. Senza server viene rimosso il sovraccarico del provisioning, della configurazione e della gestione dei server per il back-end per dispositivi mobili.

## <a name="internet-of-things-iot"></a>Internet delle cose (IoT)

Si riferisce a oggetti fisici collegati in rete. Sono talvolta denominate "dispositivi connessi" o "Smart Device". Tutti gli elementi delle automobili e dei distributori automatici possono essere connessi e inviare informazioni che variano dall'inventario ai dati dei sensori, ad esempio temperatura e umidità. Nell'organizzazione, l'Internet delle cose fornisce miglioramenti ai processi aziendali tramite il monitoraggio e l'automazione. I dati relativi alle cose possono essere usati per regolare il clima in un magazzino di grandi dimensioni o per tenere traccia dell'inventario attraverso la supply chain. Gli spessori possono rilevare i rilevamenti chimici e chiamare il reparto antincendio quando viene rilevato fumo.

Il volume elevato di dispositivi e informazioni impone spesso un'architettura basata su eventi per indirizzare ed elaborare i messaggi. Senza server è una soluzione ideale per diversi motivi:

* Abilita la scalabilità Man mano che aumenta il volume di dispositivi e dati.
* Consente di aggiungere nuovi endpoint per supportare nuovi dispositivi e sensori.
* Semplifica il controllo delle versioni indipendente, in modo che gli sviluppatori possano aggiornare la logica di business per un dispositivo specifico senza dover distribuire l'intero sistema.
* Resilienza e minor tempo di inattività.

La pervasività di Internet delle cose ha comportato diversi prodotti senza server che si concentrano in modo specifico sulle problematiche, ad esempio l' [Hub Azure](https://docs.microsoft.com/azure/iot-hub). Senza server automatizza le attività, ad esempio *la*registrazione del dispositivo, l'applicazione dei criteri, il monitoraggio e persino la distribuzione di codice nei dispositivi perimetrali. Il bordo si riferisce a dispositivi come sensori e attuatori connessi a, ma non a una parte attiva di Internet.

>[!div class="step-by-step"]
>[Precedente](architecture-approaches.md)
>[Successivo](serverless-architecture-considerations.md)
