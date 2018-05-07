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
ms.openlocfilehash: f1af991d7db9bfeeb0737e65a0517629f359f4a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="accessing-data-service-resources-wcf-data-services"></a>Accesso alle risorse di un servizio dati (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] supporta il [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] per esporre dati come feed con risorse indirizzabili tramite URI. Queste risorse sono rappresentate in base alle convenzioni entità-relazione del [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md). In questo modello le entità rappresentano unità operative di dati che corrispondono a tipi di dati in un dominio di applicazione, ad esempio clienti, ordini, elementi e prodotti. L'accesso ai dati di entità e la relativa modifica sono possibili mediante la semantica REST (Representational State Transfer), in particolare i verbi GET, PUT, POST e DELETE standard HTTP.  
  
## <a name="addressing-resources"></a>Indirizzamento di risorse  
 In [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] i dati esposti vengono indirizzati dal modello di dati tramite un URI. Ad esempio, l'URI seguente restituisce un feed che corrisponde al set di entità Customers, che contiene le voci per tutte le istanze del tipo di entità Customer:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers  
```  
  
 Le entità dispongono di proprietà speciali denominate chiavi di entità. Una chiave di entità viene usata per identificare in modo univoco una singola entità in un set di entità. In questo modo è possibile indirizzare un'istanza specifica di un tipo di entità nel set di entità. L'URI seguente restituisce ad esempio una voce per un'istanza specifica del tipo di entità Customer che presenta un valore chiave corrispondente ad `ALFKI`:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')  
```  
  
 Le proprietà primitive e complesse di un'istanza di entità possono anche essere indirizzate singolarmente. L'URI seguente restituisce ad esempio un elemento XML che contiene il valore della proprietà `ContactName` per un cliente (Customer) specifico:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName  
```  
  
 Se si include l'endpoint `$value` nell'URI precedente, nel messaggio di risposta viene restituito solo il valore della proprietà primitiva. Nell'esempio seguente viene restituita solo la stringa "Maria Anders" senza l'elemento XML:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName/$value  
```  
  
 Le relazioni tra entità vengono definite mediante associazioni nel modello di dati. Queste associazioni consentono di indirizzare entità correlate usando le proprietà di navigazione di un'istanza di entità. Una proprietà di navigazione può restituire una sola entità correlata, nel caso di una relazione molti-a-uno, o un set di entità correlate, nel caso di una relazione uno-a-molti. L'URI seguente restituisce ad esempio un feed che corrisponde al set di tutte le entità Order correlate a un cliente specifico:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders  
```  
  
 Le relazioni, che in genere sono bidirezionali, sono rappresentate da una coppia di proprietà di navigazione. Al contrario della relazione mostrata nell'esempio precedente, l'URI seguente restituisce un riferimento all'entità Customer alla quale appartiene un'entità Order specifica:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/Customer  
```  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] consente inoltre alle risorse di indirizzo in base ai risultati delle espressioni di query. Ciò consente di filtrare i set di risorse in base a un'espressione valutata. L'URI seguente consente ad esempio di filtrare le risorse per restituire solo gli ordini per il cliente specificato inviati dal 22 settembre 1997:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=ShippedDate gt datetime'1997-09-22T00:00:00'  
```  
  
 Per ulteriori informazioni, vedere [OData: convenzioni URI](http://go.microsoft.com/fwlink/?LinkId=185564).  
  
## <a name="system-query-options"></a>Opzioni di query di sistema  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] definisce un set di opzioni di query di sistema che è possibile utilizzare per eseguire operazioni di query tradizionali in base alle risorse, quali filtro, ordinamento e paging. Ad esempio, l'URI seguente restituisce il set di tutti i `Order` entità, insieme alle `Order_Detail` entità, i codici di avviamento postali non terminano con `100`:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')&$expand=Order_Details&$orderby=ShipCity  
```  
  
 Le voci del feed restituito vengono inoltre ordinate in base al valore della proprietà ShipCity degli ordini.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] supporta i seguenti [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] opzioni di query di sistema:  
  
|Opzione query|Descrizione|  
|------------------|-----------------|  
|`$orderby`|Definisce un tipo di ordinamento predefinito per le entità del feed restituito. Nella query seguente il feed restituito dei clienti viene ordinato in base al paese e alla città:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$orderby=Country,City`<br /><br /> Per ulteriori informazioni, vedere [OData: opzione Query di sistema OrderBy ($orderby)](http://go.microsoft.com/fwlink/?LinkId=186968).|  
|`$top`|Specifica il numero di entità da includere nel feed restituito. Nell'esempio seguente vengono ignorati i primi 10 clienti, quindi vengono restituiti i successivi 10:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Per ulteriori informazioni, vedere [OData: opzione Query di sistema Top ($top)](http://go.microsoft.com/fwlink/?LinkId=186969).|  
|`$skip`|Specifica il numero di entità da ignorare prima di avviare la restituzione delle entità nel feed. Nell'esempio seguente vengono ignorati i primi 10 clienti, quindi vengono restituiti i successivi 10:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Per ulteriori informazioni, vedere [OData: opzione Query di sistema Skip ($skip)](http://go.microsoft.com/fwlink/?LinkId=186971).|  
|`$filter`|Definisce un'espressione che filtra le entità restituite nel feed in base a criteri specifici. Questa opzione query supporta un set di operatori di confronto logici, di operatori aritmetici e di funzioni di query predefinite che consentono di valutare l'espressione di filtro. Nell'esempio seguente vengono restituiti tutti gli ordini in cui i codici di avviamento postale non terminano con 100:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')`<br /><br /> Per ulteriori informazioni, vedere [OData: opzione Query di sistema di filtro ($filter)](http://go.microsoft.com/fwlink/?LinkId=186972).|  
|`$expand`|Specifica quali entità correlate vengono restituite dalla query. Le entità correlate vengono incluse come feed o voce inline con l'entità restituita dalla query. Nell'esempio seguente viene restituito l'ordine per il cliente "ALFKI" insieme ai dettagli relativi agli elementi di ogni ordine:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$expand=Order_Details`<br /><br /> Per ulteriori informazioni, vedere [OData: opzione sistema Expand Query ($expand)](http://go.microsoft.com/fwlink/?LinkId=186973).|  
|`$select`|Indica che le proprietà dell'entità devono essere restituite nella proiezione. Per impostazione predefinita, tutte le proprietà di un'entità vengono restituite in un feed. Nella query seguente vengono restituite solo tre proprietà dell'entità `Customer`:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$select=CustomerID,CompanyName,City`<br /><br /> Per ulteriori informazioni, vedere [OData: opzione Select System Query ($select)](http://go.microsoft.com/fwlink/?LinkID=186076).|  
|`$inlinecount`|Richiede l'inclusione nel feed di un conteggio del numero di entità restituite nel feed stesso. Per ulteriori informazioni, vedere [OData: opzione Query di sistema Inlinecount ($inlinecount)](http://go.microsoft.com/fwlink/?LinkId=186975).|  
  
## <a name="addressing-relationships"></a>Indirizzamento delle relazioni  
 Oltre all'indirizzamento di set di entità e le istanze di entità, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] consente inoltre di indirizzare le associazioni che rappresentano le relazioni tra entità. Questa funzionalità è necessaria per creare o modificare una relazione tra due istanze di entità, ad esempio lo spedizioniere correlato a un determinato ordine nel database Northwind di esempio. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] supporta un `$link` operatore per indirizzare in modo specifico le associazioni tra entità. L'URI seguente viene ad esempio specificato in un messaggio di richiesta PUT HTTP per modificare lo spedizioniere per l'ordine specificato in un nuovo spedizioniere.  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/$links/Shipper  
```  
  
 Per ulteriori informazioni, vedere [OData: indirizzamento di collegamenti tra voci](http://go.microsoft.com/fwlink/?LinkId=187351).  
  
## <a name="consuming-the-returned-feed"></a>Utilizzo del feed restituito  
 L'URI di un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] risorse consentono di eseguire indirizzo entità dati esposti dal servizio. Quando si immette un URI nel campo dell'indirizzo di un Web browser, un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] rappresentazione del feed della risorsa richiesta viene restituito. Per ulteriori informazioni, vedere il [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Sebbene un Web browser possa risultare utile per verificare che una risorsa del servizio dati restituisce i dati previsti, servizi di dati di produzione che possono inoltre creare, aggiornare ed eliminare dati vengono in genere eseguiti dal codice dell'applicazione o in una pagina Web linguaggi di scripting. Per ulteriori informazioni, vedere [utilizza un servizio dati in un'applicazione Client](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Sito Web Open Data Protocol](http://go.microsoft.com/fwlink/?LinkID=182204)
