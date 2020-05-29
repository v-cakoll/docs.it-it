---
title: Accesso alle risorse di un servizio dati (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, querying
- getting started, WCF Data Services
- querying the data service [WCF Data Service]
- WCF Data Services, getting started
- WCF Data Services, accessing data
ms.assetid: 9665ff5b-3e3a-495d-bf83-d531d5d060ed
ms.openlocfilehash: 6a44d61f29fad7fa7d5304deb8b1e329478bc5b4
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202014"
---
# <a name="accessing-data-service-resources-wcf-data-services"></a>Accesso alle risorse di un servizio dati (WCF Data Services)
WCF Data Services supporta il Open Data Protocol (OData) per esporre i dati come feed con risorse indirizzabili da URI. Queste risorse vengono rappresentate in base alle convenzioni entità-relazione del [Entity Data Model](../adonet/entity-data-model.md). In questo modello le entità rappresentano unità operative di dati che corrispondono a tipi di dati in un dominio di applicazione, ad esempio clienti, ordini, elementi e prodotti. L'accesso ai dati di entità e la relativa modifica sono possibili mediante la semantica REST (Representational State Transfer), in particolare i verbi GET, PUT, POST e DELETE standard HTTP.  
  
## <a name="addressing-resources"></a>Indirizzamento di risorse  
 In OData è possibile indirizzare tutti i dati esposti dal modello di dati usando un URI. L'URI seguente restituisce ad esempio un feed, ovvero il set di entità Customers, che contiene le voci per tutte le istanze del tipo di entità Customer:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers>
  
 Le entità dispongono di proprietà speciali denominate chiavi di entità. Una chiave di entità viene usata per identificare in modo univoco una singola entità in un set di entità. In questo modo è possibile indirizzare un'istanza specifica di un tipo di entità nel set di entità. L'URI seguente restituisce ad esempio una voce per un'istanza specifica del tipo di entità Customer che presenta un valore chiave corrispondente ad `ALFKI`:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')>
  
 Le proprietà primitive e complesse di un'istanza di entità possono anche essere indirizzate singolarmente. L'URI seguente restituisce ad esempio un elemento XML che contiene il valore della proprietà `ContactName` per un cliente (Customer) specifico:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName>
  
 Se si include l'endpoint `$value` nell'URI precedente, nel messaggio di risposta viene restituito solo il valore della proprietà primitiva. Nell'esempio seguente viene restituita solo la stringa "Maria Anders" senza l'elemento XML:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName/$value>
  
 Le relazioni tra entità vengono definite mediante associazioni nel modello di dati. Queste associazioni consentono di indirizzare entità correlate usando le proprietà di navigazione di un'istanza di entità. Una proprietà di navigazione può restituire una sola entità correlata, nel caso di una relazione molti-a-uno, o un set di entità correlate, nel caso di una relazione uno-a-molti. L'URI seguente restituisce ad esempio un feed che corrisponde al set di tutte le entità Order correlate a un cliente specifico:  
  
<https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders>
  
 Le relazioni, che in genere sono bidirezionali, sono rappresentate da una coppia di proprietà di navigazione. Al contrario della relazione mostrata nell'esempio precedente, l'URI seguente restituisce un riferimento all'entità Customer alla quale appartiene un'entità Order specifica:  
  
<https://services.odata.org/Northwind/Northwind.svc/Orders(10643)/Customer>
  
 OData consente inoltre di indirizzare le risorse in base ai risultati delle espressioni di query. In questo modo è possibile filtrare i set di risorse in base a un'espressione valutata. L'URI seguente consente ad esempio di filtrare le risorse per restituire solo gli ordini per il cliente specificato inviati dal 22 settembre 1997:  
  
`https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=ShippedDate gt datetime'1997-09-22T00:00:00'`
  
 Per ulteriori informazioni, vedere [OData: convenzioni URI](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/).
  
## <a name="system-query-options"></a>Opzioni di query di sistema  
 OData definisce un set di opzioni di query di sistema che è possibile usare per eseguire operazioni di query tradizionali su risorse quali filtro, ordinamento e paging. Ad esempio, l'URI seguente restituisce il set di tutte le `Order` entità, insieme alle `Order_Detail` entità correlate, i codici postali di che non terminano con `100` :  
  
`https://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')&$expand=Order_Details&$orderby=ShipCity`
  
 Le voci del feed restituito vengono inoltre ordinate in base al valore della proprietà ShipCity degli ordini.  
  
 WCF Data Services supporta le seguenti opzioni di query di sistema OData:  
  
|Opzione query|Descrizione|  
|------------------|-----------------|  
|`$orderby`|Definisce un tipo di ordinamento predefinito per le entità del feed restituito. Nella query seguente il feed restituito dei clienti viene ordinato in base al paese e alla città:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers?$orderby=Country,City>`|  
|`$top`|Specifica il numero di entità da includere nel feed restituito. Nell'esempio seguente vengono ignorati i primi 10 clienti, quindi vengono restituiti i successivi 10:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`|  
|`$skip`|Specifica il numero di entità da ignorare prima di avviare la restituzione delle entità nel feed. Nell'esempio seguente vengono ignorati i primi 10 clienti, quindi vengono restituiti i successivi 10:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`|  
|`$filter`|Definisce un'espressione che filtra le entità restituite nel feed in base a criteri specifici. Questa opzione query supporta un set di operatori di confronto logici, di operatori aritmetici e di funzioni di query predefinite che consentono di valutare l'espressione di filtro. Nell'esempio seguente vengono restituiti tutti gli ordini in cui i codici di avviamento postale non terminano con 100:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')`|  
|`$expand`|Specifica quali entità correlate vengono restituite dalla query. Le entità correlate vengono incluse come feed o voce inline con l'entità restituita dalla query. Nell'esempio seguente viene restituito l'ordine per il cliente "ALFKI" insieme ai dettagli relativi agli elementi di ogni ordine:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$expand=Order_Details`|  
|`$select`|Indica che le proprietà dell'entità devono essere restituite nella proiezione. Per impostazione predefinita, tutte le proprietà di un'entità vengono restituite in un feed. Nella query seguente vengono restituite solo tre proprietà dell'entità `Customer`:<br /><br /> `https://services.odata.org/Northwind/Northwind.svc/Customers?$select=CustomerID,CompanyName,City`|  
|`$inlinecount`|Richiede l'inclusione nel feed di un conteggio del numero di entità restituite nel feed stesso.|  
  
## <a name="addressing-relationships"></a>Indirizzamento delle relazioni  
 Oltre ad affrontare i set di entità e le istanze di entità, OData consente inoltre di indirizzare le associazioni che rappresentano le relazioni tra entità. Questa funzionalità è necessaria per creare o modificare una relazione tra due istanze di entità, ad esempio lo spedizioniere correlato a un determinato ordine nel database Northwind di esempio. OData supporta un `$link` operatore per indirizzare in modo specifico le associazioni tra entità. L'URI seguente viene ad esempio specificato in un messaggio di richiesta PUT HTTP per modificare lo spedizioniere per l'ordine specificato in un nuovo spedizioniere.  
  
`https://services.odata.org/Northwind/Northwind.svc/Orders(10643)/$links/Shipper`
  
 Per ulteriori informazioni, vedere `3.2. Addressing Links between Entries` la sezione in [OData: convenzioni URI](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/).
  
## <a name="consuming-the-returned-feed"></a>Utilizzo del feed restituito  
 L'URI di una risorsa OData consente di indirizzare i dati di entità esposti dal servizio. Quando si immette un URI nel campo dell'indirizzo di una Web browser, viene restituita una rappresentazione del feed OData della risorsa richiesta. Per ulteriori informazioni, vedere la [Guida introduttiva WCF Data Services](quickstart-wcf-data-services.md). Sebbene l'uso di un browser possa risultare utile per verificare che una risorsa del servizio dati restituisca i dati previsti, l'accesso ai servizi dati di produzione che sono inoltre in grado di creare, aggiornare ed eliminare dati viene in genere eseguito tramite linguaggi di codice delle applicazioni o di script in una pagina Web. Per ulteriori informazioni, vedere [utilizzo di un servizio dati in un'applicazione client](using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Sito Web Open Data Protocol](https://www.odata.org/)
