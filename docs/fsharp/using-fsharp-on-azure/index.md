---
title: Uso di F# in Azure
description: "Guida all'uso dei servizi di Azure con F #"
author: sylvanc
ms.date: 09/22/2016
ms.openlocfilehash: f074ac192f6dedbadf8132430cf27dc5865e6371
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501820"
---
# <a name="using-f-on-azure"></a>Uso di F# in Azure

F# è un linguaggio eccezionale per la programmazione cloud ed è spesso usato per scrivere applicazioni Web, servizi cloud, microservizi ospitati nel cloud, e per l'elaborazione di dati scalabili.

Nelle sezioni seguenti sono disponibili informazioni su come usare una serie di servizi di Azure con F#.

> [!NOTE]
> Se un servizio specifico di Azure non è illustrato in questa documentazione, vedere la documentazione su Funzioni di Azure o su .NET per tale servizio. Alcuni servizi di Azure non dipendono dal linguaggio e non richiedono documentazione specifica per il linguaggio, pertanto non solo elencati in questa sezione.

## <a name="using-azure-virtual-machines-with-f"></a>Uso delle macchine virtuali di Azure con F\#

Azure supporta un'ampia gamma di configurazioni di macchine virtuali (VM). Per informazioni, vedere [Macchine virtuali di Linux e Azure](https://azure.microsoft.com/services/virtual-machines/).

Per installare F# in una macchina virtuale per l'esecuzione, la compilazione e/o gli script, vedere [Using F# on Linux](https://fsharp.org/use/linux) (Uso di F# in Linux) e [Using F# on Windows](https://fsharp.org/use/windows) (Uso di F# in Windows).

## <a name="using-azure-functions-with-f"></a>Uso di Funzioni di Azure con F\#

[Funzioni di Azure](https://azure.microsoft.com/services/functions/) è una soluzione che consente di eseguire facilmente piccole parti di codice, o "funzioni", nel cloud. È possibile scrivere solo il codice necessario per il problema effettivo, senza preoccuparsi di un'intera applicazione o dell'infrastruttura necessaria per eseguirlo. Le funzioni sono connesse agli eventi nell'Archiviazione di Azure e a altre risorse ospitate nel cloud. I dati vengono usati nelle funzioni F# tramite gli argomenti delle funzioni. È possibile usare il linguaggio di sviluppo preferito e lasciare ad Azure l'esecuzione della scalabilità necessaria.

Funzioni di Azure supporta F# come linguaggio di prima classe con un'efficiente, reattiva e scalabile esecuzione del codice F#. Per la documentazione di riferimento sull'uso di F# con Funzioni di Azure, vedere [Guida di riferimento per gli sviluppatori di Funzioni di Azure in F#](/azure/azure-functions/functions-reference-fsharp).

Altre risorse per l'uso di Funzioni di Azure e F#:

* [Scale Up Azure Functions in F# Using Suave](https://blog.tamizhvendan.in/blog/2016/09/19/scale-up-azure-functions-in-f-number-using-suave/) (Estendere Funzioni di Azure in F# tramite Suave)
* [How to create Azure function in F#](https://www.mnie.me/azurefunctions) (Come creare un funzione di Azure in F#)
* [Uso del provider di tipi di Azure con funzioni di Azure](https://compositional-it.com/blog/2017/08-30-using-the-azure-type-provider-with-azure-functions/index.html)

## <a name="using-azure-storage-with-f"></a>Uso dell'Archiviazione di Azure con F\#

L'Archiviazione di Azure è un livello di base di servizi di archiviazione che si basa su affidabilità, disponibilità e scalabilità per soddisfare le esigenze dei clienti. I programmi F # possono interagire direttamente con i servizi di archiviazione di Azure, usando le tecniche descritte negli articoli seguenti.

* [Introduzione all'archiviazione BLOB di Azure con F#](blob-storage.md)
* [Introduzione all'archiviazione file di Azure con F#](file-storage.md)
* [Introduzione all'archiviazione code di Azure con #](queue-storage.md)
* [Introduzione all'archiviazione tabelle di Azure con F#](table-storage.md)

L'Archiviazione di Azure può essere anche usata con Funzioni di Azure tramite una configurazione dichiarativa anziché tramite chiamate API esplicite. Vedere [Azure Functions triggers and bindings for Azure Storage](/azure/azure-functions/functions-bindings-storage) (Trigger e associazioni di Funzioni di Azure per l'Archiviazione di Azure) che include esempi di F#.

## <a name="using-azure-app-service-with-f"></a>Uso del Servizio app di Azure con F\#

Il [Servizio app di Azure](https://azure.microsoft.com/services/app-service/) è una piattaforma cloud per creare efficaci app per cloud e per dispositivi mobili, che si connettono a dati nel cloud o locali.

* [F# Azure Web API example](https://github.com/fsprojects/azure-webapi-example) (Esempio di API Web di Azure per F#)
* [Hosting F# in a web application on Azure](https://github.com/isaacabraham/fsharp-demonstrator) (Hosting di F# in un'applicazione Web di Azure)

## <a name="using-apache-spark-with-f-with-azure-hdinsight"></a>Uso di Apache Spark con F# e Azure HDInsight

[Apache Spark per Azure HDInsight](https://azure.microsoft.com/services/hdinsight/apache-spark/) è un framework open source di elaborazione che esegue applicazioni di analitica di dati su larga scala. Azure rende semplice e conveniente la distribuzione di Apache Spark. Sviluppare l'applicazione Spark in F# usando [Mobius](https://github.com/Microsoft/Mobius), un'API .NET per Spark.

* [Implementing Spark Apps in F# using Mobius](https://github.com/Microsoft/Mobius/blob/master/notes/spark-fsharp-mobius.md) (Implementazione di app Spark in F# tramite Mobius)
* [Example F# Spark Apps using Mobius](https://github.com/Microsoft/Mobius/tree/master/examples/fsharp) (Esempio di app Spark in F# tramite Mobius)

## <a name="using-azure-cosmos-db-with-f"></a>Uso di Azure Cosmos DB con F\#

[Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db) è un servizio NoSQL per app a disponibilità elevata distribuite a livello globale.

Azure Cosmos DB può essere utilizzato con F # in due modi:

1. Tramite la creazione di funzioni di Azure F # che reagiscono o comportano modifiche alle raccolte di Azure Cosmos DB. Vedere [associazioni Azure Cosmos DB per funzioni di Azure](/azure/azure-functions/functions-bindings-cosmosdb)o
2. Tramite l' [API di Azure Cosmos DB .NET SDK per SQL](/azure/cosmos-db/sql-api-sdk-dotnet). Gli esempi correlati sono in C#.

## <a name="using-azure-event-hubs-with-f"></a>Uso di hub eventi di Azure con F\#

Gli [hub eventi di Azure](https://azure.microsoft.com/services/event-hubs/) offrono l'inserimento di telemetria con scalabilità cloud da siti Web, app e dispositivi.

Gli hub di Azure DocumentDB possono essere usati con F# in due modi:

1. Tramite la creazione di Funzioni di Azure per F# attivati da eventi. Vedere [Azure Function triggers for Event Hubs](/azure/azure-functions/functions-bindings-event-hubs) (Trigger di Funzioni di Azure per gli hub di eventi), oppure
2. con l'uso di [.NET SDK per Azure](/azure/event-hubs/event-hubs-csharp-ephcs-getstarted). Si noti che questi esempi sono basati su C#.

## <a name="using-azure-notification-hubs-with-f"></a>Uso degli hub di notifica di Azure con F\#

Gli [hub di notifica di Azure](/azure/notification-hubs/) sono un'infrastruttura push multipiattaforma e con scalabilità orizzontale, che consentono di inviare notifiche push mobili da qualsiasi back-end (nel cloud o locale) a qualsiasi piattaforma mobile.

Gli hub di notifica di Azure possono essere usati con F# in due modi:

1. Tramite la creazione di Funzioni di Azure per F# che inviano risultati a un hub di notifica. Vedere [Azure Function output triggers for Notification Hubs](/azure/azure-functions/functions-bindings-notification-hubs) (Trigger di output di Funzioni di Azure per gli hub di notifica), oppure
2. con l'uso di [.NET SDK per Azure](https://docs.microsoft.com/archive/blogs/azuremobile/push-notifications-using-notification-hub-and-net-backend). Si noti che questi esempi sono basati su C#.

## <a name="implementing-webhooks-on-azure-with-f"></a>Implementazione di webhook in Azure con F\#

Un [webhook](https://en.wikipedia.org/wiki/Webhook) è un callback attivato tramite una richiesta Web. I webhook vengono usati da siti, quali GitHub, per segnalare eventi.

I webhook possono essere implementati in F# e ospitati in Azure tramite una [funzione di Azure in F# con un'associazione ai webhook](/azure/azure-functions/functions-bindings-http-webhook).

## <a name="using-webjobs-with-f"></a>Uso di processi Web con F\#

I [processi Web](/azure/app-service-web/web-sites-create-web-jobs) sono programmi eseguibili in un'app Web di un servizio app in tre modi: su richiesta, in modo continuo o in una pianificazione.

[Esempio di un processo Web per F#](https://github.com/jrr/webjob-project-examples)

## <a name="implementing-timers-on-azure-with-f"></a>Implementazione di timer in Azure con F\#

Le funzioni di chiamata dei trigger timer si basano su pianificazione, tempo e ricorrenza.

I timer possono essere implementati in F# e ospitati in Azure tramite una [funzione di Azure in F# con un trigger di timer](/azure/azure-functions/functions-bindings-timer).

## <a name="deploying-and-managing-azure-resources-with-f-scripts"></a>Distribuzione e gestione di risorse di Azure con script F#

Le macchine virtuali di Azure possono essere distribuite e gestite a livello di codice a partire dagli script F# tramite le API e i pacchetti Microsoft.Azure.Management. Ad esempio, vedere [Introduzione alle librerie di gestione per .NET](https://msdn.microsoft.com/library/dn722415.aspx) e [Uso di Azure Resource Manager](/azure/azure-resource-manager/resource-manager-deployment-model).

Analogamente, le altre risorse di Azure possono essere anche distribuite e gestite dagli script F# usando gli stessi componenti. Ad esempio, è possibile creare account di archiviazione, distribuire servizi cloud di Azure, creare istanze di Azure Cosmos DB e gestire Hub notifica di Azure a livello di codice dagli script F #.

L'uso di script F# per distribuire e gestire risorse non è in genere necessario. Ad esempio, le risorse di Azure possono anche essere distribuite direttamente dalle descrizioni dei modelli JSON, che possono essere parametrizzate. Vedere [Procedure consigliate per la creazione di modelli di Azure Resource Manager](/azure/azure-resource-manager/resource-manager-template-best-practices) che include esempi, quali i [modelli di avvio rapido di Azure](https://azure.microsoft.com/resources/templates/).

## <a name="other-resources"></a>Altre risorse

* [Documentazione completa su tutti i servizi di Azure](/azure/)
