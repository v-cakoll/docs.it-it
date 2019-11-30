---
title: Libreria client WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: 74b3e50c36f0b3238b8fb74ca1ea1b336e0983c0
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568777"
---
# <a name="wcf-data-services-client-library"></a>Libreria client WCF Data Services
Qualsiasi applicazione può interagire con un servizio dati basato su Open Data Protocol (OData) se può inviare una richiesta HTTP ed elaborare il feed OData restituito da un servizio dati. Questa interoperabilità consente di accedere ai servizi basati su OData da un'ampia gamma di applicazioni abilitate per il Web. WCF Data Services include librerie client che forniscono un'esperienza di programmazione più completa quando si utilizzano feed OData da .NET Framework o da applicazioni basate su Silverlight.  
  
 Le due classi principali della libreria client sono <xref:System.Data.Services.Client.DataServiceContext> e <xref:System.Data.Services.Client.DataServiceQuery%601>. La classe <xref:System.Data.Services.Client.DataServiceContext> incapsula operazioni supportate su un servizio dati specificato. Sebbene i servizi OData siano senza stato, il contesto non lo è. Pertanto, è possibile utilizzare la classe <xref:System.Data.Services.Client.DataServiceContext> per mantenere lo stato sul client tra le interazioni con il servizio dati per supportare funzionalità quali la gestione delle modifiche. Questa classe consente inoltre di gestire le identità e di rilevare le modifiche. La classe <xref:System.Data.Services.Client.DataServiceQuery%601> rappresenta una query su un set di entità specifico.  
  
 Questa sezione descrive come usare le librerie client per accedere ai dati di un'applicazione client .NET Framework e modificarli. Per ulteriori informazioni sull'utilizzo della WCF Data Services libreria client con un'applicazione basata su Silverlight, vedere [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=186016). Sono disponibili altre librerie client che consentono di utilizzare un feed OData in altri tipi di applicazioni. Per ulteriori informazioni, vedere [OData SDK](https://go.microsoft.com/fwlink/?LinkID=185796).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Generazione della libreria client del servizio dati](generating-the-data-service-client-library-wcf-data-services.md)  
 Viene descritto come generare una libreria client e le classi del servizio dati client basate su feed OData.  
  
 [Esecuzione di query sul servizio dati](querying-the-data-service-wcf-data-services.md)  
 Viene descritto come eseguire una query su un servizio dati da un'applicazione basata su Framework .NET usando le librerie client.  
  
 [Caricamento di contenuto posticipato](loading-deferred-content-wcf-data-services.md)  
 Viene descritto come caricare contenuto aggiuntivo non incluso nella risposta alla query iniziale.  
  
 [Aggiornamento del servizio dati](updating-the-data-service-wcf-data-services.md)  
 Viene descritto come creare, modificare ed eliminare entità e relazioni usando le librerie client.  
  
 [Operazioni asincrone](asynchronous-operations-wcf-data-services.md)  
 Vengono descritte le funzionalità fornite dalle librerie client per l'uso di un servizio dati in modo asincrono.  
  
 [Esecuzione di operazioni in batch](batching-operations-wcf-data-services.md)  
 Viene descritto come inviare più richieste al servizio dati in un unico batch usando le librerie client.  
  
 [Associazione di dati a controlli](binding-data-to-controls-wcf-data-services.md)  
 Viene descritto come associare controlli a un feed OData restituito da un servizio dati.  
  
 [Operazioni del servizio di chiamata](calling-service-operations-wcf-data-services.md)  
 Viene descritto come usare la libreria client per chiamare le operazioni del servizio.  
  
 [Gestione del contesto del servizio dati](managing-the-data-service-context-wcf-data-services.md)  
 Vengono descritte le opzioni per la gestione del comportamento della libreria client.  
  
 [Utilizzo di dati binari](working-with-binary-data-wcf-data-services.md)  
 Viene descritto come accedere e apportare modifiche ai dati binari restituiti dal servizio dati come flusso di dati.  
  
## <a name="see-also"></a>Vedere anche

- [Definizione di WCF Data Services](defining-wcf-data-services.md)
- [Introduzione](getting-started-with-wcf-data-services.md)
