---
title: Scenari aziendali di esempio e casi d'uso per le app senza server
description: Impara a usare senza server un approccio pratico accedendo ad esempi che variano da elaborazione di immagini a back-end per dispositivi mobili e pipeline ETL.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5f0d7a4c5cd736d1168ec76c1c0ea19627505f15
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787885"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>Scenari di business serverless e casi d'uso

Esistono molti casi d'uso e scenari per le applicazioni senza server. Questo capitolo include esempi che illustrano i diversi scenari. Gli scenari includono collegamenti alla documentazione correlata e ai repository di codice sorgente pubblico. Gli esempi in questo capitolo consentono di iniziare a creare e implementare soluzioni senza server.

## <a name="analyze-and-archive-images"></a>Analizza e archivia le immagini

Questo esempio illustra gli eventi senza server (griglia di eventi), i flussi di lavoro (app per la logica) e il codice (funzioni di Azure). Viene inoltre illustrato come integrare con un'altra risorsa, in questo caso Servizi cognitivi per l'analisi delle immagini.

Un'applicazione console consente di passare un collegamento a un URL nel Web. L'app pubblica l'URL come messaggio di griglia di eventi. In parallelo, un'app per le funzioni senza server e un'app per la logica sottoscrivono il messaggio. L'app per le funzioni senza server serializza l'immagine nell'archivio BLOB. Archivia anche le informazioni nell'archiviazione tabelle di Azure. I metadati archiviano l'URL dell'immagine originale e il nome dell'immagine BLOB. L'app per la logica interagisce con l'API Visione personalizzata per analizzare l'immagine e creare una didascalia generata dal computer. La didascalia viene archiviata nella tabella dei metadati.

![Analizzare e archiviare l'architettura delle immagini](./media/image-processing-example.png)

Un'applicazione a pagina singola (SPA) separata chiama una funzione senza server per ottenere un elenco di immagini e metadati. Per ogni immagine, viene chiamata un'altra funzione che recapita i dati dell'immagine dall'archivio. Il risultato finale è una raccolta con didascalie automatiche.

![Raccolta immagini automatizzata](./media/automated-image-gallery.png)

Il repository completo e le istruzioni per compilare l'app per la logica sono disponibili qui: [colla di griglia di eventi](https://github.com/JeremyLikness/Event-Grid-Glue).

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a>Client multipiattaforma per dispositivi mobili con Novell. Forms e Functions

Vedere come implementare una semplice funzione di Azure senza server nel portale Web di Azure o in Visual Studio. Creazione di un client con Novell. Forms in esecuzione in Android, iOS e Windows. L'applicazione viene quindi perfezionata per usare JavaScript Object Notation (JSON) come mezzo di comunicazione tra il server e i client mobili con un back-end senza server.

Per altre informazioni, vedere [implementazione di una semplice funzione di Azure con un client Novell. Forms](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/).

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a>Genera un mosaico foto con riconoscimento immagine senza server

L'esempio usa funzioni di Azure e servizi cognitivi Microsoft Servizio visione artificiale personalizzato per generare un mosaico foto da un'immagine di input. Il modello viene sottoposto a training per riconoscere le immagini. Quando viene caricata un'immagine, l'immagine viene riconosciuta e la ricerca viene eseguita con Bing. L'immagine originale viene ricomposta usando i risultati della ricerca.

![Foto e mosaico di Orlando Eye](./media/orlando-eye-both.png)

Ad esempio, è possibile eseguire il training del modello con i punti di interesse di Orlando, ad esempio Orlando Eye. Visione personalizzata riconoscerà un'immagine di Orlando Eye e la funzione creerà un mosaico foto composto dai risultati della ricerca immagini Bing per "Orlando Eye".

Per altre informazioni, vedere [Generatore di mosaici foto di funzioni di Azure](https://github.com/Azure-Samples/functions-dotnet-photo-mosaic).

## <a name="migrate-an-existing-application-to-the-cloud"></a>Eseguire la migrazione di un'applicazione esistente nel cloud

Come illustrato nei capitoli precedenti, è comune adottare un'architettura a più livelli per ospitare l'applicazione in locale. Anche se la migrazione delle risorse "così come è", l'uso di macchine virtuali è il percorso meno rischioso per il cloud, molte aziende scelgono di usare l'opportunità di effettuare il refactoring delle applicazioni. Fortunatamente, il refactoring non deve necessariamente essere un lavoro "tutto o niente". Infatti, è possibile eseguire la migrazione dell'app, quindi sostituire i componenti con le controparti native del cloud.

L'applicazione usa la funzionalità proxy di funzioni di Azure per abilitare il refactoring di un endpoint dal codice locale legacy a un endpoint senza server.

![Architettura di migrazione](./media/migration-architecture.png)

Il proxy fornisce un singolo endpoint API che viene aggiornato per reindirizzare le singole richieste Man mano che vengono spostate in funzioni senza server.

È possibile visualizzare un video che illustra l'intera migrazione: [Lift-and-Shift con funzioni di Azure senza server](https://channel9.msdn.com/Events/Connect/2017/E102). Accedere al codice di esempio: [Bring your own app](https://github.com/JeremyLikness/bring-own-app-connect-17).

## <a name="parse-a-csv-file-and-insert-into-a-database"></a>Analizzare un file CSV e inserirlo in un database

L'estrazione, la trasformazione e il caricamento (ETL) è una funzione aziendale comune che integra sistemi diversi. Gli approcci tradizionali spesso comportano la configurazione di server FTP dedicati, quindi la distribuzione dei processi pianificati per analizzare i file e tradurli per l'uso aziendale. L'architettura senza server semplifica il processo perché un trigger può essere attivato quando il file viene caricato. Funzioni di Azure affronta attività come ETL grazie alla sua composizione ideale di piccoli frammenti di codice che si concentrano su un problema specifico.

![Screenshot che illustra il processo di analisi CSV.](./media/serverless-business-scenarios/csv-parse-database-import.png)

Per il codice sorgente e un Lab pratico, vedere il [Lab di importazione CSV](https://github.com/JeremyLikness/azure-fn-file-process-hol).

## <a name="shorten-links-and-track-metrics"></a>Abbreviare i collegamenti e tenere traccia delle metriche

Gli strumenti di abbreviazione dei collegamenti hanno inizialmente permesso di codificare gli URL in brevi post di Twitter per adattarsi al limite di 140 caratteri Sono cresciuti per includere diversi usi, in genere per tenere traccia dei click-through per l'analisi. Lo scenario di abbreviazione del collegamento è un'applicazione completamente senza server che consente di gestire le metriche dei collegamenti e dei report.

Funzioni di Azure viene usato per gestire un'applicazione a pagina singola (SPA) che consente di incollare l'URL lungo e generare URL brevi. Gli URL sono contrassegnati per tenere traccia di elementi come campagne (argomenti) e medi (ad esempio, i social network ai quali vengono pubblicati i collegamenti). Il codice breve viene archiviato in archiviazione tabelle di Azure come chiave, con l'URL lungo come valore. Quando si fa clic sul collegamento breve, un'altra funzione Cerca l'URL lungo, invia un reindirizzamento e inserisce le informazioni sull'evento in una coda. Un'altra funzione di Azure elabora la coda e inserisce le informazioni in Azure Cosmos DB.

![Architettura di abbreviare i collegamenti](./media/link-shortener-architecture.png)

È quindi possibile creare un dashboard Power BI per raccogliere informazioni dettagliate sui dati raccolti. Nel back-end Application Insights fornisce metriche importanti. I dati di telemetria includono il tempo necessario per il reindirizzamento dell'utente medio e il tempo necessario per accedere all'archiviazione tabelle di Azure.

![Esempio di Power BI](./media/power-bi-example.png)

Il repository dell'abbreviazione del collegamento completo con le istruzioni è disponibile qui: [abbreviare l'URL senza server](https://github.com/jeremylikness/serverless-url-shortener). Per informazioni su una versione semplificata, vedere [archiviazione di Azure per app .NET senza server in pochi minuti](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/).

## <a name="verify-device-connectivity-using-a-ping"></a>Verificare la connettività del dispositivo con un ping

L'esempio è costituito da un hub Azure e da una funzione di Azure. Un nuovo messaggio nell'hub Internet attiva la funzione di Azure. Il codice senza server invia lo stesso contenuto del messaggio al dispositivo che lo ha inviato. Il progetto include tutte le configurazioni di codice e distribuzione necessarie per la soluzione.

Per altre informazioni, vedere [ping dell'hub Azure](https://github.com/Azure-Samples/iot-hub-node-ping).

## <a name="recommended-resources"></a>Risorse consigliate

- [Generatore di mosaici foto di funzioni di Azure](https://github.com/Azure-Samples/functions-dotnet-photo-mosaic)
- [Ping dell'hub Azure](https://github.com/Azure-Samples/iot-hub-node-ping)
- [Archiviazione di Azure per app .NET senza server in pochi minuti](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/)
- [Porta la tua app](https://github.com/JeremyLikness/bring-own-app-connect-17)
- [Lab di importazione CSV](https://github.com/JeremyLikness/azure-fn-file-process-hol)
- [Colla griglia di eventi](https://github.com/JeremyLikness/Event-Grid-Glue)
- [Implementazione di una semplice funzione di Azure con un client Novell. Forms](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)
- [Lift-and-Shift con funzioni di Azure senza server](https://channel9.msdn.com/Events/Connect/2017/E102)
- [Abbreviazione URL senza server](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
>[Precedente](orchestration-patterns.md)
>[Successivo](serverless-conclusion.md)
