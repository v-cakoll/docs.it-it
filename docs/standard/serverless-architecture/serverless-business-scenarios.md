---
title: Scenari di business di esempio e casi d'uso per le app senza server
description: Informazioni su modalità senza server con un approccio pratico per l'accesso a esempi che spaziano dall'elaborazione di immagini a pipeline ETL e di back-end per dispositivi mobili.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 177fb1d7f79a0067ab185e520778b593d4b8eaf6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62017220"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>Scenari di business serverless e casi d'uso

Esistono diversi casi d'uso e scenari per le applicazioni senza server. In questo capitolo sono inclusi esempi che illustrano i diversi scenari. Gli scenari includono i collegamenti alla documentazione correlata e repository di codice sorgente pubblico. Gli esempi in questo capitolo consentono di iniziare a usare in modo autonomo, compilazione e implementazione di soluzioni senza server.

## <a name="analyze-and-archive-images"></a>Analizzare e archiviare le immagini

Questo esempio illustra gli eventi senza server (griglia di eventi), i flussi di lavoro (App per la logica) e codice (funzioni di Azure). Viene inoltre illustrato come integrare con un'altra risorsa, in questo caso servizi cognitivi di analisi delle immagini.

Un'applicazione console consente di passare un collegamento a un URL nel web. L'app pubblica l'URL come un messaggio di griglia di eventi. In parallelo, un'app per le funzioni senza server e un'app per la logica sottoscrivere il messaggio. L'app per le funzioni senza server serializza l'immagine nell'archivio blob. Archivia anche le informazioni nell'archiviazione tabelle di Azure. I metadati vengono archiviati il nome dell'immagine di blob e l'URL dell'immagine originale. L'app per la logica di interazione con l'API visione artificiale personalizzato per analizzare l'immagine e creare una didascalia generati dal computer. La didascalia viene archiviata nella tabella dei metadati.

![Analizzare e archiviare l'architettura di immagini](./media/image-processing-example.png)

Un'applicazione separata singola pagina (SPA) chiama una funzione senza server per ottenere un elenco di immagini e i metadati. Per ogni immagine, chiama un'altra funzione che recapita i dati dell'immagine nell'archivio. Il risultato finale è una raccolta con i sottotitoli automatici.

![Raccolta automatica di immagini](./media/automated-image-gallery.png)

Il repository completo e istruzioni per compilare l'app per la logica sono disponibili qui: [Associazione di griglia di eventi](https://github.com/JeremyLikness/Event-Grid-Glue).

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a>Client per dispositivi mobili multipiattaforma con xamarin. Forms e funzioni

Informazioni su come implementare una semplice funzione di Azure senza server nel portale Web di Azure o in Visual Studio. Compilare un client con xamarin. Forms in esecuzione su Android, iOS e Windows. L'applicazione viene quindi perfezionata per l'uso di JavaScript Object Notation (JSON) come un mezzo di comunicazione tra il server e i client per dispositivi mobili con un back-end senza server.

Per altre informazioni, vedere [implementando una semplice funzione di Azure con un client di xamarin. Forms](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a>Generare un mosaico di foto con riconoscimento delle immagini senza server

L'esempio Usa funzioni di Azure e servizio visione artificiale personalizzato Microsoft Cognitive Services per generare un mosaico di foto da un'immagine di input. Il modello è in grado di riconoscere le immagini. Quando viene caricata un'immagine, riconosce l'immagine e Cerca con Bing. L'immagine originale è ricomposto usando i risultati della ricerca.

![Mosaico e Orlando occhio foto](./media/orlando-eye-both.png)

Ad esempio, è possibile eseguire il training del modello con riferimenti a Orlando, ad esempio l'occhio del lettore Orlando. Servizio visione artificiale personalizzato riconoscerà un'immagine dell'occhio del lettore a Orlando, e la funzione creerà un mosaico di foto composto da risultati della ricerca immagini Bing di "Orlando occhio".

Per altre informazioni, vedere [generatore di funzioni di Azure foto Mosaico](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/).

## <a name="migrate-an-existing-application-to-the-cloud"></a>Eseguire la migrazione di un'applicazione esistente nel cloud

Come illustrato nei precedenti capitoli, è comune per adottare un'architettura a più livelli per ospitare l'applicazione in locale. Anche se la migrazione di risorse "così com'è" uso di macchine virtuali è il percorso almeno a rischio nel cloud, molte società sceglie di usare l'opportunità di eseguire il refactoring delle applicazioni. Fortunatamente, refactoring non deve essere un lavoro richiesto "o niente". In effetti, è possibile migrare l'app quindi a fasi sostituire componenti con le controparti nativa cloud.

L'applicazione usa la funzionalità proxy di funzioni di Azure per abilitare il refactoring di un endpoint da codice legacy da sito locale a un endpoint senza server.

![Architettura di migrazione](./media/migration-architecture.png)

Il proxy fornisce un singolo endpoint API che viene aggiornato per reindirizzare singole richieste, come vengono spostate nelle funzioni senza server.

È possibile visualizzare un video che illustra l'intera migrazione: [Lift- and -shift con funzioni di Azure senza server](https://channel9.msdn.com/Events/Connect/2017/E102). Accedere al codice di esempio: [Portare la propria app](https://github.com/JeremyLikness/bring-own-app-connect-17).

## <a name="parse-a-csv-file-and-insert-into-a-database"></a>Analizzare un file CSV e inserire in un database

Estrarre, trasformare e caricamento (ETL) è una funzione di business comuni che si integra sistemi diversi. Gli approcci tradizionali spesso necessario configurare il server FTP dedicati quindi distribuisce i processi pianificati per analizzare i file e convertirli per l'uso aziendale. Architettura senza server semplifica il processo perché un trigger può essere generato quando il file viene caricato. Attività del tackles funzioni di Azure, come ETL attraverso la composizione ideale del piccole porzioni di codice che puntano a un problema specifico.

![Screenshot che mostra il processo di analisi csv.](./media/serverless-business-scenarios/csv-parse-database-import.png)

Per il codice sorgente e un laboratorio pratico, vedere [CSV importare lab](https://github.com/JeremyLikness/azure-fn-file-process-hol).

## <a name="shorten-links-and-track-metrics"></a>Abbreviare i collegamenti e tenere traccia delle metriche

Gli strumenti di collegamento ad abbreviare originariamente ha contribuito a codificare gli URL in breve twitter post per rispettare il limite di 140 caratteri. È stata estesa e include diversi utilizzi, più comunemente per tenere traccia di click-through per analitica. Lo scenario di shortener collegamento è un'applicazione interamente senza server che gestisce i collegamenti e riporta le metriche.

Funzioni di Azure viene usato per servire una singola pagina applicazione (SPA) che consente di incollare l'URL lungo e generare gli URL brevi. Gli URL vengono contrassegnati per tenere traccia di elementi quali le campagne (argomenti) e supporti (ad esempio i social network che i collegamenti vengono registrati in). Il codice breve viene archiviato in archiviazione tabelle di Azure come chiave, con l'URL come valore long. Quando si fa clic sul collegamento breve, un'altra funzione Cerca l'URL lungo, invia un reindirizzamento e inserisce le informazioni sull'evento in una coda. Un'altra funzione di Azure elabora le code e inserisce le informazioni in Azure Cosmos DB.

![Collegamento shortener architettura](./media/link-shortener-architecture.png)

È quindi possibile creare un dashboard di Power BI per raccogliere informazioni dettagliate sui dati raccolti. Nel back-end, Application Insights fornisce metriche importanti. I dati di telemetria includono il tempo necessario per l'utente medio reindirizzare e il tempo necessario per accedere all'archiviazione tabelle di Azure.

![Esempio di Power BI](./media/power-bi-example.png)

Il repository shortener il collegamento completo con le istruzioni è disponibile qui: [Strumento di abbreviazione URL senza server](https://github.com/jeremylikness/serverless-url-shortener). È possibile leggere su una versione semplificata di seguito: [Archiviazione di Azure per le app .NET senza server in pochi minuti](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/).

## <a name="verify-device-connectivity-using-a-ping"></a>Verificare la connettività del dispositivo tramite un ping

L'esempio è costituito da un IoT Hub di Azure e una funzione di Azure. Un nuovo messaggio nell'IoT Hub attiva la funzione di Azure. Il codice senza server invia contenuto lo stesso messaggio al dispositivo che l'ha inviata. Il progetto contiene tutta la configurazione di distribuzione e di codice necessaria per la soluzione.

Per altre informazioni, vedere [ping dell'IoT Hub di Azure](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/).

## <a name="recommended-resources"></a>Risorse consigliate

* [Generatore di mosaico foto funzioni Azure](https://azure.microsoft.com/resources/samples/functions-dotnet-photo-mosaic/)
* [Ping dell'IoT Hub di Azure](https://azure.microsoft.com/resources/samples/iot-hub-node-ping/)
* [Archiviazione di Azure per le app .NET senza server in pochi minuti](https://blogs.msdn.microsoft.com/webdev/2018/01/25/azure-storage-for-serverless-net-apps-in-minutes/)
* [Portare la propria app](https://github.com/JeremyLikness/bring-own-app-connect-17)
* [Lab di importazione CSV](https://github.com/JeremyLikness/azure-fn-file-process-hol)
* [Associazione di griglia di eventi](https://github.com/JeremyLikness/Event-Grid-Glue)
* [Implementazione di una semplice funzione di Azure con un client di xamarin. Forms](https://azure.microsoft.com/resources/samples/functions-xamarin-getting-started/)
* [Lift- and -shift con funzioni di Azure senza server](https://channel9.msdn.com/Events/Connect/2017/E102)
* [Strumento di abbreviazione URL senza server](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
>[Precedente](orchestration-patterns.md)
>[Successivo](serverless-conclusion.md)