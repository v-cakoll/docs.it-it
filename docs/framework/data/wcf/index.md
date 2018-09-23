---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 9ece2fe051855d0fd39556f56a4343ead2c437bc
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46702806"
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5

WCF Data Services (precedentemente noto come "ADO.NET Data Services") è un componente di .NET Framework che consente di creare servizi che usano il [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] per esporre e utilizzare dati sul Web o su intranet tramite la semantica di [ (REST) Representational state transfer](https://go.microsoft.com/fwlink/?LinkId=113919). In OData i dati vengono esposti come risorse indirizzabili tramite URI. Per accedere ai dati e apportarvi modifiche è possibile utilizzare i verbi HTTP standard GET, PUT, POST e DELETE. OData utilizza le convenzioni entità-relazione del [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) per esporre risorse come set di entità correlate da associazioni.

WCF Data Services utilizza il protocollo OData per l'indirizzamento e l'aggiornamento delle risorse. In questo modo, è possibile accedere a questi servizi da qualsiasi client che supporta OData. OData consente di richiedere e scrivere dati nelle risorse utilizzando formati di trasferimento noti: Atom, un set di standard per lo scambio e l'aggiornamento dei dati come XML e JavaScript Object Notation (JSON), un formato di scambio dei dati basata su testo ampiamente utilizzato in AJAX applicazione.

WCF Data Services può esporre dati provengono da varie origini come feed OData. Strumenti di Visual Studio semplificano la creazione di un servizio basato su OData usando un modello di dati ADO.NET Entity Framework. È anche possibile creare feed OData basate su classi common language runtime (CLR) e i dati anche con associazione tardiva o senza tipo.

WCF Data Services include inoltre un set di librerie client, una per le applicazioni client di .NET Framework generale e un'altra in modo specifico per le applicazioni basate su Silverlight. Queste librerie client forniscono un modello di programmazione basato su oggetti quando si accede a un feed OData da ambienti quali .NET Framework e Silverlight.

## <a name="where-should-i-start"></a>Da dove iniziare

In base ai tuoi interessi, prendere in considerazione Introduzione a WCF Data Services in uno degli argomenti seguenti.

Passare subito a...

-   [Guida rapida](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

-   [Introduzione](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

-   [Guida rapida di Silverlight](https://go.microsoft.com/fwlink/?LinkID=192782)

-   [Guida rapida di Silverlight per lo sviluppo per Windows Phone](https://go.microsoft.com/fwlink/?LinkID=214535)

Visualizzi un codice...

-   [Guida rapida](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

-   [Procedura: Eseguire query sul servizio dati](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

-   [Procedura: Associare dati a elementi Windows Presentation Foundation](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)

Si vuole conoscere ulteriori informazioni su OData...

 -   [Whitepaper: Introduzione a OData](https://go.microsoft.com/fwlink/?LinkId=220867)

-   [Sito Web Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=184554)

-   [OData: SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

-   [OData: Domande frequenti](https://go.microsoft.com/fwlink/?LinkId=185867)

Voglio vedere alcuni video...

-   [Guida per i principianti di WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=220864)

-   [Video per sviluppatori di WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=220861)

-   [OData: Sito Web degli sviluppatori](https://go.microsoft.com/fwlink/?LinkId=185866)

Desidera vedere esempi end-to-end...

-   [Esempi di documentazione di WCF Data Services nella raccolta di esempi MSDN](https://go.microsoft.com/fwlink/?LinkID=220865)

-   [Altri esempi di WCF Data Services nella raccolta di esempi MSDN](https://go.microsoft.com/fwlink/?LinkId=220866)

-   [OData: SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

Integrazione con Visual Studio

-   [Generazione della libreria client del servizio dati](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)

-   [Creazione del servizio dati](../../../../docs/framework/data/wcf/creating-the-data-service.md)

-   [Provider di Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)

Attività possibili

-   [Panoramica](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

-   [Whitepaper: Introduzione a OData](https://go.microsoft.com/fwlink/?LinkId=220867)

-   [Scenari di applicazione](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)

Desidero utilizzare Silverlight...

-   [Guida rapida di Silverlight](https://go.microsoft.com/fwlink/?LinkID=192782)

-   [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149)

-   [Introduzione a Silverlight](https://go.microsoft.com/fwlink/?LinkId=148366)

Desidero utilizzare LINQ...

-   [Esecuzione di query sul servizio dati](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)

-   [Considerazioni su LINQ](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)

-   [Procedura: Eseguire query sul servizio dati](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

Devo ancora alcune informazioni...

-   [Blog del team di WCF Data Services](https://go.microsoft.com/fwlink/?LinkID=150511)

-   [Risorse](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)

-   [Centro per sviluppatori di WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=220868)

-   [Sito Web Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a>In questa sezione

 [Panoramica](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

 Fornisce una panoramica delle caratteristiche e delle funzionalità disponibili in WCF Data Services.

 [Novità in WCF Data Services](https://msdn.microsoft.com/library/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)

 Descrive le nuove funzionalità di WCF Data Services e il supporto per nuove funzionalità di OData.

 [Introduzione](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

 Viene descritto come esporre e utilizzare feed OData tramite WCF Data Services.

 [Definizione di WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)

 Viene descritto come creare e configurare un servizio dati che espone feed OData.

 [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

 Viene descritto come usare le librerie client per utilizzare feed OData da un'applicazione client .NET Framework.

## <a name="see-also"></a>Vedere anche

- [REST (Representational State Transfer)](https://go.microsoft.com/fwlink/?LinkId=113919)
