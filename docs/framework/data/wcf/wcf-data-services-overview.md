---
title: Panoramica di WCF Data Services
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services
- WCF Data Services, about
ms.assetid: 7924cf94-c9a6-4015-afc9-f5d22b1743bb
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 88d586ead18e4129707728733029c735083b477c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-data-services-overview"></a>Panoramica di WCF Data Services
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]consente la creazione e uso di servizi dati per il Web o una rete intranet tramite la [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]Consente di esporre i dati come risorse indirizzabili tramite URI. In questo modo è possibile accedere ai dati e modificarli utilizzando la semantica REST (Representational State Transfer), in particolare i verbi GET, PUT, POST e DELETE standard HTTP. Questo argomento offre cenni preliminari sia sui modelli che sulle pratiche definiti da [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] e fornisce informazioni sulle funzioni disponibili in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] che consentono di utilizzare [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] nelle applicazioni basate su .NET Framework.  
  
## <a name="address-data-as-resources"></a>Indirizzare i dati come risorse  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] espone i dati come risorse indirizzabili tramite URI. I percorsi delle risorse vengono creati in base alle convenzioni entità-relazione di Entity Data Model. In questo modello le entità rappresentano unità operative di dati in un dominio applicazione, ad esempio clienti, ordini, elementi e prodotti. Per ulteriori informazioni, vedere [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md).  
  
 In [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] le risorse di entità vengono indirizzate come set di entità contenenti istanze dei tipi di entità. Ad esempio, l'URI `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders` restituisce tutti gli ordini di `Northwind` servizio dati che sono correlati al cliente con un `CustomerID` valore`ALFKI.`  
  
 Le espressioni di query consentono di eseguire operazioni di query tradizionali, quali filtro, ordinamento e paging, sulle risorse. L'URI `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=Freight gt 50` filtra ad esempio le risorse in modo da restituire solo gli ordini con un costo di spedizione superiore a 50 dollari. Per ulteriori informazioni, vedere [accesso alle risorse del servizio dati](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md).  
  
## <a name="interoperable-data-access"></a>Accesso ai dati interoperativo  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]si basa su protocolli Internet standard per creare servizi dati che interoperano con le applicazioni che non utilizzano .NET Framework. Poiché è possibile usare URI standard per i dati degli indirizzi, l'applicazione può accedere e modificare dati tramite la semantica representational state Transfer (REST), in particolare i verbi HTTP standard di GET, PUT, POST ed eliminare. In questo modo è possibile accedere a questi servizi da qualsiasi client in grado di analizzare e di accedere ai dati trasmessi su protocolli HTTP standard.  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] definisce un set di estensioni del protocollo di pubblicazione Atom (AtomPub). Per soddisfare le esigenze di applicazioni e piattaforme client diverse, supporta richieste e risposte HTTP in più formati di dati. Un feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] può rappresentare i dati nei formati Atom e JSON (JavaScript Object Notation), nonché come XML semplice. Sebbene Atom sia il formato predefinito, il formato del feed è specificato nell'intestazione della richiesta HTTP. Per ulteriori informazioni, vedere [OData: formato Atom](http://go.microsoft.com/fwlink/?LinkID=185794) e [OData: formato JSON](http://go.microsoft.com/fwlink/?LinkID=185795).  
  
 Quando si pubblicano dati come un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] si basa sulle funzioni Internet esistenti per operazioni quali la memorizzazione nella cache e l'autenticazione. A tale scopo, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] si integra con le applicazioni di hosting esistente e servizi, ad esempio ASP.NET, Windows Communication Foundation (WCF) e Internet Information Services (IIS).  
  
## <a name="storage-independence"></a>Indipendenza dall'archiviazione  
 Sebbene le risorse vengano indirizzate in base a un modello entità-relazione, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] espone i feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] indipendentemente dall'origine dati sottostante. Quando [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] accetta una richiesta HTTP per una risorsa identificata da un URI, la richiesta viene deserializzata e una rappresentazione di tale richiesta viene passata a un provider di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Questo provider traduce la richiesta in un formato specifico dell'origine dati ed esegue la richiesta sull'origine dati sottostante. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] realizza l'indipendenza di archiviazione separando il modello concettuale per l'indirizzamento delle risorse previste da [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] dallo schema specifico dell'origine dati sottostante.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] si integra con ADO.NET Entity Framework per consentire la creazione di servizi dati che espongono dati relazionali. È possibile usare gli strumenti di Entity Data Model per creare un modello di dati contenente risorse indirizzabili come entità e definire contemporaneamente il mapping tra questo modello e le tabelle nel database sottostante. Per ulteriori informazioni, vedere [Provider di Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md).  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]consente inoltre di creare servizi dati che espongono strutture di dati che restituiscono un'implementazione del <xref:System.Linq.IQueryable%601> interfaccia. In questo modo è possibile creare servizi dati che espongono dati di tipi di .NET Framework. Le operazioni di creazione, aggiornamento ed eliminazione sono supportate quando si implementa anche l'interfaccia <xref:System.Data.Services.IUpdatable>. Per ulteriori informazioni, vedere [Provider di Reflection](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md).  
  
 Per un'illustrazione di come [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] si integra con questi provider di dati, vedere il diagramma dell'architettura più avanti in questo argomento.  
  
## <a name="custom-business-logic"></a>Logica di business personalizzata  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]Consente di aggiungere logica di business personalizzata a un servizio dati tramite operazioni del servizio e intercettori. Le operazioni del servizio sono metodi definiti nel server che possono essere indirizzati tramite URI allo stesso modo delle risorse di dati. Le operazioni del servizio possono inoltre utilizzare la sintassi delle espressioni di query per filtrare e ordinare i dati restituiti da un'operazione ed eseguirne il paging. L'URI `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$orderby=OrderDate&$top=10&$skip=10` rappresenta ad esempio una chiamata a un'operazione del servizio denominata `GetOrdersByCity` nel servizio dati Northwind che restituisce gli ordini dei clienti residenti a Londra, con i risultati di paging ordinati per `OrderDate`. Per ulteriori informazioni, vedere [operazioni del servizio](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).  
  
 Gli intercettori consentono l'integrazione della logica delle applicazioni personalizzata nell'elaborazione dei messaggi di richiesta o di risposta da parte di un servizio dati. Gli intercettori vengono chiamati quando si verifica un'azione di query, inserimento, aggiornamento o eliminazione nel set di entità specificato. Un intercettore può modificare i dati, applicare criteri di autorizzazione o anche terminare l'operazione. I metodi dell'intercettore devono essere registrati in modo esplicito per un determinato set di entità esposto da un servizio dati. Per ulteriori informazioni, vedere [intercettori](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).  
  
## <a name="client-libraries"></a>Librerie client  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]definisce un set di modelli uniformi per l'interazione con i servizi dati. Questo offre l'opportunità di creare componenti riutilizzabili che si basano su questi servizi, quali librerie lato client che rendono più semplice l'uso dei servizi dati.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] include librerie client sia per le applicazioni client basate su .NET Framework che su Silverlight. Queste librerie client consentono di interagire con i servizi dati usando oggetti di .NET Framework. Supportano inoltre query basate su oggetto e query LINQ, caricamento di oggetti correlati, rilevamento di modifiche e risoluzione di identità. Per ulteriori informazioni, vedere [libreria Client di WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).  
  
 Oltre al [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] librerie client incluse in .NET Framework e Silverlight, sono disponibili altre librerie client che consentono di utilizzare un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed nelle applicazioni client, ad esempio le applicazioni PHP, AJAX e Java. Per ulteriori informazioni, vedere il [OData SDK](http://go.microsoft.com/fwlink/?LinkID=185796).  
  
## <a name="architecture-overview"></a>Panoramica dell'architettura  
 Il diagramma seguente illustra il [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] architettura per l'esposizione di [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed e l'uso di tali feed in [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-abilitato le librerie client:  
  
 ![Diagramma dell'architettura di WCF Data Services](../../../../docs/framework/data/wcf/media/astoriaservicearch.gif "AstoriaServiceArch")  
  
## <a name="see-also"></a>Vedere anche  
 [WCF Data Services 4.5](../../../../docs/framework/data/wcf/index.md)  
 [Introduzione](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 [Definizione di WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Accesso a un servizio dati (WCF Data Services)](http://msdn.microsoft.com/en-us/1e54a2b9-2ec6-4002-b8f8-c1d8df37c350)  
 [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [REST (Representational State Transfer)](http://go.microsoft.com/fwlink/?LinkId=113919)
