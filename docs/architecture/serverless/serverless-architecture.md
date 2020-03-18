---
title: Architettura senza server - App senza server
description: Esplorazione di varie architetture e app supportate da architetture senza server, tra cui app Web, dispositivi mobili e IoT.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 838dcd7b41df0d8297e1ae10f9c04a8d5b83b332
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522399"
---
# <a name="serverless-architecture"></a>Architettura serverless

Esistono molti approcci all'utilizzo di architetture [senza server.](https://azure.com/serverless) In questo capitolo vengono esaminati esempi di architetture comuni che integrano serverless. Vengono inoltre illustrate le preoccupazioni che possono rappresentare ulteriori problemi o richiedere ulteriori considerazioni durante l'implementazione di serverless. Infine, vengono forniti diversi esempi di progettazione che illustrano vari casi d'uso senza server.

Gli host senza server utilizzano spesso un livello PaaS o basato su contenitori esistente per gestire le istanze senza server. Ad esempio, Funzioni di Azure è basato sul servizio app di [Azure.For](https://docs.microsoft.com/azure/app-service/)example, Azure Functions is based on Azure App Service . Il servizio app viene usato per scalare orizzontalmente le istanze e gestire il runtime che esegue il codice di Funzioni di Azure.The App Service is used to scale out instances and manage the runtime that executes Azure Functions code. Per le funzioni basate su Windows, l'host viene eseguito come PaaS e scala il runtime di .NET. Per le funzioni basate su Linux, l'host sfrutta i contenitori.

![Architettura di Funzioni di AzureAzure Functions architecture](./media/azure-functions-architecture.png)

WebJobs Core fornisce un contesto di esecuzione per la funzione. Language Runtime esegue script, esegue librerie e ospita il framework per il linguaggio di destinazione. Ad esempio, Node.js viene utilizzato per eseguire le funzioni JavaScript e .NET Framework viene utilizzato per eseguire le funzioni c. Ulteriori informazioni sulle opzioni relative alla lingua e alla piattaforma verranno apprese più avanti in questo capitolo.

Alcuni progetti possono trarre vantaggio dall'adottare un approccio "all-in" a serverless. Le applicazioni che si basano fortemente sui microservizi possono implementare tutti i microservizi utilizzando la tecnologia senza server. La maggior parte delle app sono ibride, seguendo una progettazione a più livelli e usando senza server per i componenti che hanno senso perché i componenti sono modulari e scalabili in modo indipendente. Per dare un senso a questi scenari, in questa sezione vengono illustrati alcuni esempi di architettura comuni che usano serverless.

## <a name="full-serverless-back-end"></a>Back-end completo senza server

Il back-end completo senza server è ideale per diversi tipi di scenari, in particolare quando si creano applicazioni nuove o "green field". Un'applicazione con un'ampia area di superficie di API può trarre vantaggio dall'implementazione di ogni API come funzione senza server. Le app basate sull'architettura dei microservizi sono un altro esempio che potrebbe essere implementato come back-end completo senza server. I microservizi comunicano tra loro attraverso vari protocolli. Scenari specifici includono:

- Prodotti SaaS basati su API (ad esempio, processori di pagamenti finanziari).
- Applicazioni basate su messaggi (ad esempio: soluzione di monitoraggio dei dispositivi).
- App incentrate sull'integrazione tra servizi (ad es. applicazione di prenotazione aerea).
- Processi eseguiti periodicamente (ad esempio, pulizia del database basata su timer).
- App incentrate sulla trasformazione dei dati (ad esempio, importazione attivata dal caricamento di file).
- Estrarre i processi Di trasformazione e caricamento (ETL).

Esistono altri casi d'uso più specifici descritti più avanti in questo documento.

## <a name="monoliths-and-starving-the-beast"></a>Monoliti e "fame della bestia"

Una sfida comune è la migrazione di un'applicazione monolitica esistente nel cloud. L'approccio meno rischioso è quello di "sollevare e spostare" interamente su macchine virtuali. Molti negozi preferiscono utilizzare la migrazione come un'opportunità per modernizzare la loro base di codice. Un approccio pratico alla migrazione è chiamato "fame della bestia". In questo scenario, il monolite viene migrato "così com'è" per iniziare. Quindi, i servizi selezionati vengono modernizzati. In alcuni casi, la firma del servizio è identica all'originale: è semplicemente ospitata come funzione. I client vengono aggiornati per utilizzare il nuovo servizio anziché l'endpoint monolite. Nel frattempo, passaggi come la replica di database consentono ai microservizi di ospitare il proprio spazio di archiviazione anche quando le transazioni sono ancora gestite dal monolite. Infine, tutti i client vengono migrati nei nuovi servizi. Il monolite è "affamato" (i suoi servizi non sono più chiamati) fino a quando tutte le funzionalità sono state sostituite. La combinazione di serverless e proxy può facilitare gran parte di questa migrazione.

![Migrazione dei monoliti senza server](./media/serverless-monolith-migration.png)

Per altre informazioni su questo approccio, guardare il video: [Portare l'app nel cloud con Funzioni](https://channel9.msdn.com/Events/Connect/2017/E102)di Azure senza server.

## <a name="web-apps"></a>App Web

Le app Web sono ottimi candidati per le applicazioni senza server. Oggi esistono due approcci comuni alle app Web: basate su server e basate su client (ad esempio Applicazione a pagina singola o SPA). Le app Web basate su server usano in genere un livello middleware per emettere chiamate API per eseguire il rendering dell'interfaccia utente Web. Le applicazioni SPA effettuano chiamate all'API REST direttamente dal browser. In entrambi gli scenari, serverless può soddisfare la richiesta dell'API middleware o REST fornendo la logica di business necessaria. Un'architettura comune consiste nel sostenere un server Web statico leggero. L'applicazione a pagina singola (SPA) serve HTML, CSS, JavaScript e altre risorse del browser. L'app Web si connette quindi a un back-end di microservizi.

## <a name="mobile-back-ends"></a>Back end mobile

Il paradigma basato su eventi delle app senza server le rende ideali come back-end mobili. Il dispositivo mobile attiva gli eventi e il codice senza server viene eseguito per soddisfare le richieste. Sfruttare un modello senza server consente agli sviluppatori di migliorare la logica di business senza dover distribuire un aggiornamento completo dell'applicazione. L'approccio senza server consente inoltre ai team di condividere endpoint e lavorare in parallelo.

Gli sviluppatori di dispositivi mobili possono creare logica di business senza diventare esperti sul lato server. Tradizionalmente, le app per dispositivi mobili si connesse ai servizi locali. La creazione del livello di servizio richiedeva la comprensione della piattaforma server e del paradigma di programmazione. Gli sviluppatori hanno lavorato con le operazioni per eseguire il provisioning dei server e configurarli in modo appropriato. A volte sono stati spesi giorni o addirittura settimane per la creazione di una pipeline di distribuzione. Tutte queste sfide sono affrontate da serverless.

Serverless astrae le dipendenze lato server e consente allo sviluppatore di concentrarsi sulla logica di business. Ad esempio, uno sviluppatore di dispositivi mobili che crea app usando un framework JavaScript può creare funzioni serverless anche con JavaScript. L'host senza server gestisce il sistema operativo, un'istanza Node.js per ospitare il codice, le dipendenze del pacchetto e altro ancora. Allo sviluppatore viene fornito un semplice set di input e un modello standard per gli output. Possono quindi concentrarsi sulla compilazione e il test della logica di business. Sono quindi in grado di utilizzare le competenze esistenti per creare la logica di back-end per l'app per dispositivi mobili senza dover imparare nuove piattaforme o diventare uno "sviluppatore lato server".

![Back-end mobile senza server](./media/serverless-mobile-backend.png)

La maggior parte dei provider di servizi cloud offre prodotti serverless basati su dispositivi mobili che semplificano l'intero ciclo di vita dello sviluppo mobile. I prodotti possono automatizzare il provisioning dei database per rendere persistenti i dati, gestire i problemi di DevOps, fornire compilazioni basate su cloud e framework di test e la possibilità di creare script per i processi aziendali utilizzando il linguaggio preferito dello sviluppatore. Seguire un approccio senza server incentrato sui dispositivi mobili può semplificare il processo. Serverless elimina l'enorme sovraccarico di provisioning, configurazione e manutenzione dei server per il back-end mobile.

## <a name="internet-of-things-iot"></a>Internet delle cose

L'IoT si riferisce agli oggetti fisici collegati in rete. A volte sono indicati come "dispositivi connessi" o "dispositivi intelligenti". Tutto, dalle automobili e distributori automatici può essere collegato e inviare informazioni che vanno dall'inventario ai dati dei sensori come la temperatura e l'umidità. Nell'azienda, l'IoT fornisce miglioramenti ai processi aziendali tramite il monitoraggio e l'automazione. I dati IoT possono essere utilizzati per regolare il clima in un grande magazzino o tenere traccia dell'inventario attraverso la catena di fornitura. L'IoT può percepire le fuoriuscite di sostanze chimiche e chiamare i vigili del fuoco quando viene rilevato fumo.

L'enorme volume di dispositivi e informazioni spesso determina un'architettura basata su eventi per instradare ed elaborare i messaggi. Serverless è una soluzione ideale per diversi motivi:

- Abilita la scalabilità all'aumentare del volume dei dispositivi e dei dati.
- Accompagna l'aggiunta di nuovi endpoint per supportare nuovi dispositivi e sensori.
- Facilita il controllo delle versioni indipendente in modo che gli sviluppatori possano aggiornare la logica di business per un dispositivo specifico senza dover distribuire l'intero sistema.
- Resilienza e meno tempi di inattività.

La pervasività dell'IoT ha portato a diversi prodotti senza server che si concentrano in particolare sui problemi IoT, ad esempio [Azure IoT Hub](https://docs.microsoft.com/azure/iot-hub). Serverless automatizza attività quali la registrazione dei dispositivi, l'applicazione dei criteri, il monitoraggio e persino *la*distribuzione di codice nei dispositivi perimetrali. Il bordo si riferisce a dispositivi come sensori e attuatori che sono collegati a Internet, ma non una parte attiva.

>[!div class="step-by-step"]
>[Successivo](architecture-approaches.md)
>[precedente](serverless-architecture-considerations.md)
