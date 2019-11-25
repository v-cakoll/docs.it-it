---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 1ce152b84f17a35982a75f54b5418623ba39210f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975225"
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5

WCF Data Services (precedentemente noto come "ADO.NET Data Services") è un componente del .NET Framework che consente di creare servizi che utilizzano il Open Data Protocol (OData) per esporre e utilizzare dati sul Web o su Intranet tramite la semantica [Rest (Representational State Transfer)](https://go.microsoft.com/fwlink/?LinkId=113919). In OData i dati vengono esposti come risorse indirizzabili tramite URI. Per accedere ai dati e apportarvi modifiche è possibile utilizzare i verbi HTTP standard GET, PUT, POST e DELETE. OData utilizza le convenzioni entità-relazione del [Entity Data Model](../adonet/entity-data-model.md) per esporre le risorse come set di entità correlate da associazioni.

WCF Data Services USA il protocollo OData per l'indirizzamento e l'aggiornamento delle risorse. In questo modo, è possibile accedere a questi servizi da qualsiasi client che supporti OData. OData consente di richiedere e scrivere dati nelle risorse usando formati di trasferimento noti, ovvero Atom, un set di standard per lo scambio e l'aggiornamento di dati come XML e JavaScript Object Notation (JSON), un formato di scambio di dati basato su testo ampiamente usato in AJAX applicazioni.

WCF Data Services possibile esporre i dati originati da varie origini come feed OData. Gli strumenti di Visual Studio semplificano la creazione di un servizio basato su OData tramite un modello di dati ADO.NET Entity Framework. È anche possibile creare feed OData in base a classi Common Language Runtime (CLR) e anche a dati ad associazione tardiva o non tipizzati.

WCF Data Services include inoltre un set di librerie client, una per le applicazioni client .NET Framework generali e un'altra specifica per le applicazioni basate su Silverlight. Queste librerie client forniscono un modello di programmazione basato su oggetti quando si accede a un feed OData da ambienti quali il .NET Framework e Silverlight.

## <a name="where-should-i-start"></a>Da dove iniziare

A seconda dei propri interessi, prendere in considerazione la Guida introduttiva a WCF Data Services in uno degli argomenti seguenti.

Passare subito a...

- [Guida rapida](quickstart-wcf-data-services.md)

- [Introduzione](getting-started-with-wcf-data-services.md)

- [Guida rapida di Silverlight](https://go.microsoft.com/fwlink/?LinkID=192782)

- [Guida rapida di Silverlight per lo sviluppo per Windows Phone](https://go.microsoft.com/fwlink/?LinkID=214535)

Mostra solo codice...

- [Guida rapida](quickstart-wcf-data-services.md)

- [Procedura: Eseguire query sul servizio dati](how-to-execute-data-service-queries-wcf-data-services.md)

- [Procedura: Associare dati a elementi Windows Presentation Foundation](bind-data-to-wpf-elements-wcf-data-services.md)

Desidero saperne di più su OData...

- [Whitepaper: Introduzione a OData](https://go.microsoft.com/fwlink/?LinkId=220867)

- [Sito Web Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=184554)

- [OData: SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

- [OData: Domande frequenti](https://go.microsoft.com/fwlink/?LinkId=185867)

Desidero guardare alcuni video...

- [Guida per i principianti di WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=220864)

- [Video per sviluppatori di WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=220861)

- [OData: Sito Web degli sviluppatori](https://go.microsoft.com/fwlink/?LinkId=185866)

Si desidera visualizzare gli esempi end-to-end...

- [Esempi di documentazione di WCF Data Services nella raccolta di esempi MSDN](https://go.microsoft.com/fwlink/?LinkID=220865)

- [Altri esempi di WCF Data Services nella raccolta di esempi MSDN](https://go.microsoft.com/fwlink/?LinkId=220866)

- [OData: SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

Integrazione con Visual Studio

- [Generazione della libreria client del servizio dati](generating-the-data-service-client-library-wcf-data-services.md)

- [Creazione del servizio dati](creating-the-data-service.md)

- [Provider di Entity Framework](entity-framework-provider-wcf-data-services.md)

Attività possibili

- [Panoramica](wcf-data-services-overview.md)

- [Whitepaper: Introduzione a OData](https://go.microsoft.com/fwlink/?LinkId=220867)

- [Scenari di applicazione](application-scenarios-wcf-data-services.md)

Si desidera utilizzare Silverlight...

- [Guida rapida di Silverlight](https://go.microsoft.com/fwlink/?LinkID=192782)

- [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149)

- [Introduzione a Silverlight](https://go.microsoft.com/fwlink/?LinkId=148366)

Si vuole usare LINQ...

- [Esecuzione di query sul servizio dati](querying-the-data-service-wcf-data-services.md)

- [Considerazioni su LINQ](linq-considerations-wcf-data-services.md)

- [Procedura: Eseguire query sul servizio dati](how-to-execute-data-service-queries-wcf-data-services.md)

Ho ancora bisogno di altre informazioni...

- [Blog del team di WCF Data Services](https://go.microsoft.com/fwlink/?LinkID=150511)

- [Risorse](wcf-data-services-resources.md)

- [Centro per sviluppatori di WCF Data Services](https://go.microsoft.com/fwlink/?LinkId=220868)

- [Sito Web Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a>Contenuto della sezione

[Panoramica](wcf-data-services-overview.md)

Viene fornita una panoramica delle caratteristiche e delle funzionalità disponibili in WCF Data Services.

[Novità di WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))

Vengono descritte le nuove funzionalità di WCF Data Services e il supporto per le nuove funzionalità OData.

[Introduzione](getting-started-with-wcf-data-services.md)

Viene descritto come esporre e utilizzare feed OData utilizzando WCF Data Services.

[Definizione di WCF Data Services](defining-wcf-data-services.md)

Viene descritto come creare e configurare un servizio dati che espone feed OData.

[Libreria client WCF Data Services](wcf-data-services-client-library.md)

Viene descritto come utilizzare le librerie client per utilizzare feed OData da un'applicazione client .NET Framework.

## <a name="see-also"></a>Vedere anche

- [REST (Representational State Transfer)](https://go.microsoft.com/fwlink/?LinkId=113919)
