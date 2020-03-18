---
title: Scenari aziendali e casi d'uso di esempio per le app senza serverSample business scenarios and use cases for serverless apps
description: Imparare senza server con un approccio pratico accedendo a campioni che vanno dall'elaborazione delle immagini ai back-end mobili e alle pipeline ETL.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5f0d7a4c5cd736d1168ec76c1c0ea19627505f15
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76787885"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>Scenari di business serverless e casi d'uso

Esistono molti casi d'uso e scenari per le applicazioni senza server. Questo capitolo include esempi che illustrano i diversi scenari. Gli scenari includono collegamenti alla documentazione correlata e ai repository di codice sorgente pubblico. Gli esempi in questo capitolo consentono di iniziare a creare soluzioni personalizzate per la creazione e l'implementazione di soluzioni senza server.

## <a name="analyze-and-archive-images"></a>Analizzare e archiviare le immagini

In questo esempio vengono illustrati gli eventi senza server (griglia di eventi), i flussi di lavoro (app per la logica) e il codice (funzioni di Azure). Viene inoltre illustrato come eseguire l'integrazione con un'altra risorsa, in questo caso Servizi cognitivi per l'analisi delle immagini.

Un'applicazione console consente di passare un collegamento a un URL sul Web. L'app pubblica l'URL come messaggio della griglia di eventi. In parallelo, un'app per le funzioni senza server e un'app per la logica sottoscrivono il messaggio. L'app per le funzioni senza server serializza l'immagine nell'archiviazione BLOB. Archivia inoltre le informazioni in Archiviazione tabelle di Azure.It also stores information in Azure Table Storage. I metadati archiviano l'URL dell'immagine originale e il nome dell'immagine BLOB. L'app per la logica interagisce con l'API di visione personalizzata per analizzare l'immagine e creare una didascalia generata dal computer. La didascalia viene archiviata nella tabella dei metadati.

![Analizzare e archiviare l'architettura delle immagini](./media/image-processing-example.png)

Un'applicazione a pagina singola (SPA) separata chiama una funzione senza server per ottenere un elenco di immagini e metadati. Per ogni immagine, chiama un'altra funzione che fornisce i dati dell'immagine dall'archivio. Il risultato finale è una galleria con didascalie automatiche.

![Galleria di immagini automatizzate](./media/automated-image-gallery.png)

Il repository completo e le istruzioni per creare l'app per la logica sono disponibili qui: [Colla griglia eventi](https://github.com/JeremyLikness/Event-Grid-Glue).

## <a name="cross-platform-mobile-client-using-xamarinforms-and-functions"></a>Client mobile multipiattaforma utilizzando Xamarin.Forms e funzioni

Informazioni su come implementare una semplice funzione di Azure senza server nel portale Web di Azure o in Visual Studio.See how to implement a simple serverless Azure Function in the Azure Web Portal or in Visual Studio. Creare un client con Xamarin.Forms che viene eseguito in Android, iOS e Windows.Build a client with Xamarin.Forms that runs on Android, iOS, and Windows. L'applicazione viene quindi perfezionata per utilizzare JavaScript Object Notation (JSON) come mezzo di comunicazione tra il server e i client mobili con un back-end serverless.

Per altre informazioni, vedere Implementazione di [una funzione di Azure semplice con un client Xamarin.Forms](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/).

## <a name="generate-a-photo-mosaic-with-serverless-image-recognition"></a>Generare un mosaico fotografico con riconoscimento di immagini senza server

L'esempio usa Funzioni di Azure e Microsoft Cognitive Services Custom Vision Service per generare un mosaico fotografico da un'immagine di input. Il modello viene sottoposto a training per riconoscere le immagini. Quando un'immagine viene caricata, riconosce l'immagine e la ricerca con Bing. L'immagine originale viene ricomposta utilizzando i risultati della ricerca.

![Orlando occhio foto e mosaico](./media/orlando-eye-both.png)

Ad esempio, puoi allenare il tuo modello con punti di riferimento di Orlando, come l'Orlando Eye. Custom Vision riconoscerà un'immagine dell'Orlando Eye e la funzione creerà un mosaico fotografico composto dai risultati di ricerca delle immagini Bing per "Orlando Eye".

Per altre informazioni, vedere [Generatore di mosaici fotografici di Funzioni di Azure](https://github.com/Azure-Samples/functions-dotnet-photo-mosaic).For more information, see Azure Functions photo mosaic generator .

## <a name="migrate-an-existing-application-to-the-cloud"></a>Eseguire la migrazione di un'applicazione esistente nel cloudMigrate an existing application to the cloud

Come illustrato nei capitoli precedenti, è comune adottare un'architettura a più livelli per ospitare l'applicazione in locale. Anche se la migrazione delle risorse "così com'è" utilizzando le macchine virtuali è il percorso meno rischioso per il cloud, molte aziende scelgono di sfruttare l'opportunità di eseguire il refactoring delle applicazioni. Fortunatamente, il refactoring non deve essere uno sforzo "tutto o niente". In effetti, è possibile eseguire la migrazione dell'app e quindi sostituire i componenti a fasi con controparti native cloud.

L'applicazione usa la funzionalità proxy di Funzioni di Azure per abilitare il refactoring di un endpoint dal codice locale legacy a un endpoint senza server.

![Architettura di migrazione](./media/migration-architecture.png)

Il proxy fornisce un singolo endpoint API che viene aggiornato per reindirizzare le singole richieste quando vengono spostate in funzioni senza server.

È possibile visualizzare un video che illustra l'intera migrazione: Passare e passare con le funzioni di [Azure senza server.](https://channel9.msdn.com/Events/Connect/2017/E102) Accedi al codice di esempio: [Porta la tua app.](https://github.com/JeremyLikness/bring-own-app-connect-17)

## <a name="parse-a-csv-file-and-insert-into-a-database"></a>Analizzare un file CSV e inserire in un database

Extract, Transform, and Load (ETL) è una funzione aziendale comune che integra sistemi diversi. Gli approcci tradizionali spesso implicano la configurazione di server FTP dedicati e la distribuzione di processi pianificati per analizzare i file e tradurli per uso aziendale. L'architettura senza server semplifica il processo perché un trigger può essere attivato quando il file viene caricato. Funzioni di Azure affronta attività come ETL attraverso la composizione ideale di piccole parti di codice che si concentrano su un problema specifico.

![Screenshot che mostra il processo di analisi csv.](./media/serverless-business-scenarios/csv-parse-database-import.png)

Per il codice sorgente e un laboratorio pratico, vedere [Laboratorio](https://github.com/JeremyLikness/azure-fn-file-process-hol)di importazione CSV .

## <a name="shorten-links-and-track-metrics"></a>Abbreviare i collegamenti e tenere traccia delle metriche

Gli strumenti di accorciamento dei link originariamente aiutavano a codificare gli URL in brevi post su Twitter per soddisfare il limite di 140 caratteri. Sono cresciuti fino a comprendere diversi usi, più comunemente per tenere traccia dei click-through per l'analisi. Lo scenario di accorto dei collegamenti è un'applicazione completamente senza server che gestisce le metriche di link e report.

Funzioni di Azure viene usato per servire un'applicazione a pagina singola (SPA) che consente di incollare l'URL lungo e generare URL brevi. Gli URL sono contrassegnati per tenere traccia di elementi come campagne (argomenti) e medium (ad esempio i social network a cui vengono pubblicati i link). Il codice breve viene archiviato in Archiviazione tabelle di Azure come chiave, con l'URL lungo come valore. Quando si fa clic sul collegamento breve, un'altra funzione cerca l'URL lungo, invia un reindirizzamento e inserisce le informazioni sull'evento in una coda. Un'altra funzione di Azure elabora la coda e inserisce le informazioni in Azure Cosmos DB.

![Architettura del shortener dei collegamenti](./media/link-shortener-architecture.png)

È quindi possibile creare un dashboard di Power BI per raccogliere informazioni dettagliate sui dati raccolti. Nel back-end, Application Insights fornisce metriche importanti. La telemetria include il tempo necessario al reindirizzamento dell'utente medio e il tempo necessario per accedere ad Archiviazione tabelle di Azure.Telemetry includes how long it takes for the average user to redirect and how long it takes to access Azure Table Storage.

![Esempio di Power BI](./media/power-bi-example.png)

Il repository completo degli abbreviazioni con le istruzioni è disponibile qui: [Serverless URL shortener](https://github.com/jeremylikness/serverless-url-shortener). È possibile leggere informazioni su una versione semplificata qui: [Archiviazione di Azure per app .NET senza server in pochi minuti.](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/)

## <a name="verify-device-connectivity-using-a-ping"></a>Verificare la connettività del dispositivo usando un pingVerify device connectivity using a ping

L'esempio è costituito da un hub IoT di Azure e da una funzione di Azure.The sample consists of an Azure IoT Hub and an Azure Function. Un nuovo messaggio nell'hub IoT attiva la funzione di Azure.A new message on the IoT Hub triggers the Azure Function. Il codice senza server invia lo stesso contenuto del messaggio al dispositivo che lo ha inviato. Il progetto dispone di tutta la configurazione di codice e distribuzione necessaria per la soluzione.

Per altre informazioni, vedere [Ping dell'hub IoT](https://github.com/Azure-Samples/iot-hub-node-ping)di Azure.For more information, see Azure IoT Hub ping .

## <a name="recommended-resources"></a>Risorse consigliate

- [Generatore di mosaici fotografici di Funzioni di AzureAzure Functions photo mosaic generator](https://github.com/Azure-Samples/functions-dotnet-photo-mosaic)
- [Ping dell'hub IoT di Azure](https://github.com/Azure-Samples/iot-hub-node-ping)
- [Archiviazione di Azure per app .NET senza server in pochi minutiAzure Storage for serverless .NET apps in minutes](https://devblogs.microsoft.com/aspnet/azure-storage-for-serverless-net-apps-in-minutes/)
- [Porta la tua app](https://github.com/JeremyLikness/bring-own-app-connect-17)
- [Laboratorio di importazione CSV](https://github.com/JeremyLikness/azure-fn-file-process-hol)
- [Colla griglia eventi](https://github.com/JeremyLikness/Event-Grid-Glue)
- [Implementazione di una funzione di Azure semplice con un client Xamarin.FormsImplementing a simple Azure Function with a Xamarin.Forms client](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/)
- [Sollevare e spostare con le funzioni di Azure senza server](https://channel9.msdn.com/Events/Connect/2017/E102)
- [Abbreviatore URL senza server](https://github.com/jeremylikness/serverless-url-shortener)

>[!div class="step-by-step"]
>[Successivo](orchestration-patterns.md)
>[precedente](serverless-conclusion.md)
