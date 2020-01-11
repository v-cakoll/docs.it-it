---
title: Panoramica di WCF Data Services
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services
- WCF Data Services, about
ms.assetid: 7924cf94-c9a6-4015-afc9-f5d22b1743bb
ms.openlocfilehash: a4121bb10de7bfe51c5fec6bc14a40ad4bdcdaf7
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900886"
---
# <a name="wcf-data-services-overview"></a>Panoramica di WCF Data Services
WCF Data Services consente la creazione e l'utilizzo di servizi dati per il Web o una Intranet tramite il Open Data Protocol (OData). OData consente di esporre i dati come risorse indirizzabili tramite URI. In questo modo è possibile accedere ai dati e modificarli utilizzando la semantica REST (Representational State Transfer), in particolare i verbi GET, PUT, POST e DELETE standard HTTP. In questo argomento viene fornita una panoramica dei modelli e delle procedure definite da OData, oltre alle funzionalità fornite da WCF Data Services per sfruttare i vantaggi di OData nelle applicazioni basate su .NET Framework.  
  
## <a name="address-data-as-resources"></a>Indirizzare i dati come risorse  
 OData espone i dati come risorse indirizzabili tramite URI. I percorsi delle risorse vengono creati in base alle convenzioni entità-relazione di Entity Data Model. In questo modello le entità rappresentano unità operative di dati in un dominio applicazione, ad esempio clienti, ordini, elementi e prodotti. Per ulteriori informazioni, vedere [Entity Data Model](../adonet/entity-data-model.md).  
  
 In OData le risorse di entità vengono indirizzate come set di entità che contiene istanze di tipi di entità. Ad esempio, l'URI <https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders> restituisce tutti gli ordini del servizio dati `Northwind` correlati al cliente con un valore `CustomerID` di `ALFKI.`  
  
 Le espressioni di query consentono di eseguire operazioni di query tradizionali, quali filtro, ordinamento e paging, sulle risorse. Ad esempio, l'URI <https://services.odata.org/Northwind/Northwind.svc/Customers( ' ALFKI ')/Orders? $filter = Freight gt 50 > Filtra le risorse per restituire solo gli ordini con un costo di spedizione maggiore di $50. Per ulteriori informazioni, vedere [accesso alle risorse del servizio dati](accessing-data-service-resources-wcf-data-services.md).  
  
## <a name="interoperable-data-access"></a>Accesso ai dati interoperativo  
 OData si basa su protocolli Internet standard per rendere interoperabili i servizi dati con applicazioni che non usano il .NET Framework. Poiché è possibile usare gli URI standard per indirizzare i dati, l'applicazione può accedere ai dati e modificarli usando la semantica REST (Representational State Transfer), in particolare i verbi HTTP standard di GET, PUT, POST e DELETE. In questo modo è possibile accedere a questi servizi da qualsiasi client in grado di analizzare e di accedere ai dati trasmessi su protocolli HTTP standard.  
  
OData definisce un set di estensioni per il protocollo di pubblicazione Atom (AtomPub). Per soddisfare le esigenze di applicazioni e piattaforme client diverse, supporta richieste e risposte HTTP in più formati di dati. Un feed OData può rappresentare i dati in Atom, JavaScript Object Notation (JSON) e come XML semplice. Sebbene Atom sia il formato predefinito, il formato del feed è specificato nell'intestazione della richiesta HTTP. Per ulteriori informazioni, vedere [OData: formato Atom](https://www.odata.org/documentation/odata-version-2-0/atom-format/) e [OData: formato JSON](https://www.odata.org/documentation/odata-version-2-0/json-format/).  
  
 Quando si pubblicano dati come feed OData, WCF Data Services si basa su altre funzionalità Internet esistenti per operazioni quali la memorizzazione nella cache e l'autenticazione. A tale scopo, WCF Data Services si integra con i servizi e le applicazioni di hosting esistenti, ad esempio ASP.NET, Windows Communication Foundation (WCF) e Internet Information Services (IIS).  
  
## <a name="storage-independence"></a>Indipendenza dall'archiviazione  
 Sebbene le risorse vengano risolte in base a un modello entità-relazione, WCF Data Services esporre i feed OData indipendentemente dall'origine dati sottostante. Dopo che WCF Data Services accetta una richiesta HTTP per una risorsa identificata da un URI, la richiesta viene deserializzata e una rappresentazione di tale richiesta viene passata a un provider di WCF Data Services. Questo provider traduce la richiesta in un formato specifico dell'origine dati ed esegue la richiesta sull'origine dati sottostante. WCF Data Services ottiene l'indipendenza di archiviazione separando il modello concettuale che risolve le risorse previste da OData dallo schema specifico dell'origine dati sottostante.  
  
 WCF Data Services si integra con il Entity Framework ADO.NET per consentire la creazione di servizi dati che espongono dati relazionali. È possibile usare gli strumenti di Entity Data Model per creare un modello di dati contenente risorse indirizzabili come entità e definire contemporaneamente il mapping tra questo modello e le tabelle nel database sottostante. Per ulteriori informazioni, vedere [Provider Entity Framework](entity-framework-provider-wcf-data-services.md).  
  
 WCF Data Services consente inoltre di creare servizi dati che espongono strutture di dati che restituiscono un'implementazione dell'interfaccia <xref:System.Linq.IQueryable%601>. In questo modo è possibile creare servizi dati che espongono dati di tipi di .NET Framework. Le operazioni di creazione, aggiornamento ed eliminazione sono supportate quando si implementa anche l'interfaccia <xref:System.Data.Services.IUpdatable>. Per ulteriori informazioni, vedere [provider di Reflection](reflection-provider-wcf-data-services.md).  
  
 Per un'illustrazione del modo in cui WCF Data Services si integra con questi provider di dati, vedere il diagramma dell'architettura più avanti in questo argomento.  
  
## <a name="custom-business-logic"></a>Logica di business personalizzata  
 WCF Data Services semplifica l'aggiunta di logica di business personalizzata a un servizio dati tramite operazioni di servizio e intercettori. Le operazioni del servizio sono metodi definiti nel server che possono essere indirizzati tramite URI allo stesso modo delle risorse di dati. Le operazioni del servizio possono inoltre utilizzare la sintassi delle espressioni di query per filtrare e ordinare i dati restituiti da un'operazione ed eseguirne il paging. L'URI `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$orderby=OrderDate&$top=10&$skip=10` rappresenta ad esempio una chiamata a un'operazione del servizio denominata `GetOrdersByCity` nel servizio dati Northwind che restituisce gli ordini dei clienti residenti a Londra, con i risultati di paging ordinati per `OrderDate`. Per altre informazioni, vedere [operazioni del servizio](service-operations-wcf-data-services.md).  
  
 Gli intercettori consentono l'integrazione della logica delle applicazioni personalizzata nell'elaborazione dei messaggi di richiesta o di risposta da parte di un servizio dati. Gli intercettori vengono chiamati quando si verifica un'azione di query, inserimento, aggiornamento o eliminazione nel set di entità specificato. Un intercettore può modificare i dati, applicare criteri di autorizzazione o anche terminare l'operazione. I metodi dell'intercettore devono essere registrati in modo esplicito per un determinato set di entità esposto da un servizio dati. Per ulteriori informazioni, vedere [intercettori](interceptors-wcf-data-services.md).  
  
## <a name="client-libraries"></a>Librerie client  
 OData definisce un set di modelli uniformi per l'interazione con i servizi dati. Questo consente di creare componenti riutilizzabili basati su questi servizi, ad esempio librerie sul lato client che semplificano l'utilizzo dei servizi dati.  
  
 WCF Data Services include librerie client sia per le applicazioni client basate su .NET Framework sia per quelle basate su Silverlight. Queste librerie client consentono di interagire con i servizi dati usando oggetti di .NET Framework. Supportano inoltre query basate su oggetto e query LINQ, caricamento di oggetti correlati, rilevamento di modifiche e risoluzione di identità. Per ulteriori informazioni, vedere [WCF Data Services libreria client](wcf-data-services-client-library.md).  
  
 Oltre alle librerie client OData incluse nel .NET Framework e con Silverlight, sono disponibili altre librerie client che consentono di utilizzare un feed OData nelle applicazioni client, ad esempio le applicazioni PHP, AJAX e Java. Per ulteriori informazioni su OData SDK, vedere [OData SDK-codice di esempio](https://www.odata.org/ecosystem/#sdk).
  
## <a name="architecture-overview"></a>Panoramica dell'architettura  
 Il diagramma seguente illustra l'architettura WCF Data Services per esporre i feed OData e usare questi feed nelle librerie client abilitate per OData:  
  
 ![Screenshot che illustra un diagramma dell'architettura WCF Data Services.](./media/wcf-data-services-overview/windows-communication-foundation-data-services-architecture.gif)  
  
## <a name="see-also"></a>Vedere anche

- [WCF Data Services 4.5](index.md)
- [Introduzione](getting-started-with-wcf-data-services.md)
- [Definizione di WCF Data Services](defining-wcf-data-services.md)
- [Accesso alle risorse del servizio dati (WCF Data Services)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd728283(v=vs.100))
- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
- [REST (Representational State Transfer)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
