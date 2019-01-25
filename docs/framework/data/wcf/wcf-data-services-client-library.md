---
title: Libreria client WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: 9af19f2ef552c5871d488c968368a9192bae9edb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656219"
---
# <a name="wcf-data-services-client-library"></a>Libreria client WCF Data Services
Un'applicazione può interagire con un servizio dati basato su [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] quando è in grado di inviare una richiesta HTTP e di elaborare il feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] restituito da un servizio dati. Questa interoperabilità consente di accedere ai servizi basati su [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] da un'ampia gamma di applicazioni Web. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] include librerie client che forniscono un'esperienza di programmazione avanzata quando si utilizzano [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed da .NET Framework o applicazioni basate su Silverlight.  
  
 Le due classi principali della libreria client sono <xref:System.Data.Services.Client.DataServiceContext> e <xref:System.Data.Services.Client.DataServiceQuery%601>. La classe <xref:System.Data.Services.Client.DataServiceContext> incapsula operazioni supportate su un servizio dati specificato. Sebbene i servizi [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] siano senza stato, non lo è il contesto. Pertanto, è possibile usare il <xref:System.Data.Services.Client.DataServiceContext> classe per mantenere lo stato del client tra interazioni con il servizio dati per supportare funzionalità quali la gestione delle modifiche. Questa classe consente inoltre di gestire le identità e di rilevare le modifiche. La classe <xref:System.Data.Services.Client.DataServiceQuery%601> rappresenta una query su un set di entità specifico.  
  
 Questa sezione descrive come usare le librerie client per accedere ai dati di un'applicazione client .NET Framework e modificarli. Per altre informazioni su come usare il [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] libreria client con un'applicazione basata su Silverlight, vedere [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=186016). Sono disponibili altre librerie client che consentono di utilizzare un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in altri tipi di applicazioni. Per altre informazioni, vedere la [OData SDK](https://go.microsoft.com/fwlink/?LinkID=185796).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Generazione della libreria client del servizio dati](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 Viene descritto come generare una libreria client e classi del servizio dati client basate su [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.  
  
 [Esecuzione di query sul servizio dati](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 Viene descritto come eseguire una query su un servizio dati da un'applicazione basata su Framework .NET usando le librerie client.  
  
 [Caricamento di contenuto posticipato](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 Viene descritto come caricare contenuto aggiuntivo non incluso nella risposta alla query iniziale.  
  
 [Aggiornamento del servizio dati](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)  
 Viene descritto come creare, modificare ed eliminare entità e relazioni usando le librerie client.  
  
 [Operazioni asincrone](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)  
 Vengono descritte le funzionalità fornite dalle librerie client per l'uso di un servizio dati in modo asincrono.  
  
 [Esecuzione di operazioni in batch](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)  
 Viene descritto come inviare più richieste al servizio dati in un unico batch usando le librerie client.  
  
 [Associazione di dati a controlli](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)  
 Viene descritto come associare controlli a un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed restituito da un servizio dati.  
  
 [Operazioni del servizio di chiamata](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md)  
 Viene descritto come usare la libreria client per chiamare le operazioni del servizio.  
  
 [Gestione del contesto del servizio dati](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md)  
 Vengono descritte le opzioni per la gestione del comportamento della libreria client.  
  
 [Utilizzo di dati binari](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)  
 Viene descritto come accedere e apportare modifiche ai dati binari restituiti dal servizio dati come flusso di dati.  
  
## <a name="see-also"></a>Vedere anche
- [Definizione di WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [Introduzione](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
