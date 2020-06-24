---
title: WCF Data Services 4.5
description: Informazioni su WCF Data Services, un componente .NET Framework che supporta i servizi per esporre e utilizzare i dati mediante la semantica REST.
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: ca6b196e8c910f97ead6d1df5b6c0dd6c49c68a4
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247753"
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5

WCF Data Services (precedentemente noto come "ADO.NET Data Services") è un componente del .NET Framework che consente di creare servizi che utilizzano il Open Data Protocol (OData) per esporre e utilizzare dati sul Web o su Intranet tramite la semantica [Rest (Representational State Transfer)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm). In OData i dati vengono esposti come risorse indirizzabili tramite URI. Per accedere ai dati e apportarvi modifiche è possibile utilizzare i verbi HTTP standard GET, PUT, POST e DELETE. OData utilizza le convenzioni entità-relazione del [Entity Data Model](../adonet/entity-data-model.md) per esporre le risorse come set di entità correlate da associazioni.

WCF Data Services USA il protocollo OData per l'indirizzamento e l'aggiornamento delle risorse. In questo modo, è possibile accedere a questi servizi da qualsiasi client che supporti OData. OData consente di richiedere e scrivere dati nelle risorse utilizzando formati di trasferimento noti, ovvero Atom, un set di standard per lo scambio e l'aggiornamento di dati come XML e JavaScript Object Notation (JSON), un formato di scambio di dati basato su testo ampiamente utilizzato nelle applicazioni AJAX.

WCF Data Services possibile esporre i dati originati da varie origini come feed OData. Gli strumenti di Visual Studio semplificano la creazione di un servizio basato su OData tramite un modello di dati ADO.NET Entity Framework. È anche possibile creare feed OData in base a classi Common Language Runtime (CLR) e anche a dati ad associazione tardiva o non tipizzati.

WCF Data Services include inoltre un set di librerie client, una per le applicazioni client .NET Framework generali e un'altra specifica per le applicazioni basate su Silverlight. Queste librerie client forniscono un modello di programmazione basato su oggetti per l'accesso a un feed OData da ambienti quali .NET Framework e Silverlight.

## <a name="where-should-i-start"></a>Da dove iniziare

A seconda dei propri interessi, prendere in considerazione la Guida introduttiva a WCF Data Services in uno degli argomenti seguenti.

Passare subito a...

- [Guida introduttiva](quickstart-wcf-data-services.md)

- [Per iniziare](getting-started-with-wcf-data-services.md)

Mostra solo codice...

- [Guida introduttiva](quickstart-wcf-data-services.md)

- [Procedura: eseguire query sul servizio dati](how-to-execute-data-service-queries-wcf-data-services.md)

- [Procedura: associare dati a elementi Windows Presentation Foundation](bind-data-to-wpf-elements-wcf-data-services.md)

Desidero saperne di più su OData...

- [White paper: Introduzione a OData](https://download.microsoft.com/download/E/5/A/E5A59052-EE48-4D64-897B-5F7C608165B8/IntroducingOData.pdf)
- [Sito Web Open Data Protocol](https://www.odata.org/)
- [OData: SDK](https://www.odata.org/ecosystem/)

Si desidera visualizzare gli esempi end-to-end...

- [Guida introduttiva a WCF Data Services](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))
- [OData SDK-codice di esempio](https://www.odata.org/ecosystem/#sdk)

Integrazione con Visual Studio

- [Generazione della libreria dati del servizio dati](generating-the-data-service-client-library-wcf-data-services.md)

- [Creazione del servizio dati](creating-the-data-service.md)

- [Provider di Entity Framework](entity-framework-provider-wcf-data-services.md)

Che si può fare con questa funzionalità?

- [Panoramica](wcf-data-services-overview.md)

- [Scenari applicativi](application-scenarios-wcf-data-services.md)

Si vuole usare LINQ...

- [Esecuzione di query sul servizio dati](querying-the-data-service-wcf-data-services.md)

- [Considerazioni su LINQ](linq-considerations-wcf-data-services.md)

- [Procedura: eseguire query sul servizio dati](how-to-execute-data-service-queries-wcf-data-services.md)

Ho ancora bisogno di altre informazioni...

- [Blog del team di WCF Data Services](https://docs.microsoft.com/archive/blogs/astoriateam/)

- [Risorse](wcf-data-services-resources.md)

## <a name="in-this-section"></a>Contenuto della sezione

[Panoramica](wcf-data-services-overview.md)

Viene fornita una panoramica delle caratteristiche e delle funzionalità disponibili in WCF Data Services.

[Novità di WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))

Vengono descritte le nuove funzionalità di WCF Data Services e il supporto per le nuove funzionalità OData.

[Per iniziare](getting-started-with-wcf-data-services.md)

Viene descritto come esporre e utilizzare feed OData utilizzando WCF Data Services.

[Definizione di WCF Data Services](defining-wcf-data-services.md)

Viene descritto come creare e configurare un servizio dati che espone feed OData.

[Libreria client WCF Data Services](wcf-data-services-client-library.md)

Viene descritto come utilizzare le librerie client per utilizzare feed OData da un'applicazione client .NET Framework.

## <a name="see-also"></a>Vedere anche

- [REST (Representational State Transfer)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
