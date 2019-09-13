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
ms.openlocfilehash: 048cbb8708aa705fe6b03491ddfa9c107a21cda1
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894356"
---
# <a name="accessing-data-service-resources-wcf-data-services"></a>Accesso alle risorse di un servizio dati (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)][!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] supporta per esporre i dati come feed con risorse indirizzabili tramite URI. Queste risorse vengono rappresentate in base alle convenzioni entità-relazione del [Entity Data Model](../adonet/entity-data-model.md). In questo modello le entità rappresentano unità operative di dati che corrispondono a tipi di dati in un dominio di applicazione, ad esempio clienti, ordini, elementi e prodotti. L'accesso ai dati di entità e la relativa modifica sono possibili mediante la semantica REST (Representational State Transfer), in particolare i verbi GET, PUT, POST e DELETE standard HTTP.  
  
## <a name="addressing-resources"></a>Indirizzamento di risorse  
 In [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] i dati esposti vengono indirizzati dal modello di dati tramite un URI. L'URI seguente restituisce ad esempio un feed che corrisponde al set di entità Customers, che contiene le voci per tutte le istanze del tipo di entità Customer:  
  
```http
https://services.odata.org/Northwind/Northwind.svc/Customers  
```  
  
 Le entità dispongono di proprietà speciali denominate chiavi di entità. Una chiave di entità viene usata per identificare in modo univoco una singola entità in un set di entità. In questo modo è possibile indirizzare un'istanza specifica di un tipo di entità nel set di entità. L'URI seguente restituisce ad esempio una voce per un'istanza specifica del tipo di entità Customer che presenta un valore chiave corrispondente ad `ALFKI`:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')  
```  
  
 Le proprietà primitive e complesse di un'istanza di entità possono anche essere indirizzate singolarmente. L'URI seguente restituisce ad esempio un elemento XML che contiene il valore della proprietà `ContactName` per un cliente (Customer) specifico:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName  
```  
  
 Se si include l'endpoint `$value` nell'URI precedente, nel messaggio di risposta viene restituito solo il valore della proprietà primitiva. Nell'esempio seguente viene restituita solo la stringa "Maria Anders" senza l'elemento XML:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName/$value  
```  
  
 Le relazioni tra entità vengono definite mediante associazioni nel modello di dati. Queste associazioni consentono di indirizzare entità correlate usando le proprietà di navigazione di un'istanza di entità. Una proprietà di navigazione può restituire una sola entità correlata, nel caso di una relazione molti-a-uno, o un set di entità correlate, nel caso di una relazione uno-a-molti. L'URI seguente restituisce ad esempio un feed che corrisponde al set di tutte le entità Order correlate a un cliente specifico:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders  
```  
  
 Le relazioni, che in genere sono bidirezionali, sono rappresentate da una coppia di proprietà di navigazione. Al contrario della relazione mostrata nell'esempio precedente, l'URI seguente restituisce un riferimento all'entità Customer alla quale appartiene un'entità Order specifica:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Orders(10643)/Customer  
```  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]consente inoltre di indirizzare le risorse in base ai risultati delle espressioni di query. In questo modo è possibile filtrare i set di risorse in base a un'espressione valutata. L'URI seguente consente ad esempio di filtrare le risorse per restituire solo gli ordini per il cliente specificato inviati dal 22 settembre 1997:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=ShippedDate gt datetime'1997-09-22T00:00:00'  
```  
  
 Per ulteriori informazioni, vedere [OData: Convenzioni](https://go.microsoft.com/fwlink/?LinkId=185564)URI.  
  
## <a name="system-query-options"></a>Opzioni di query di sistema  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]definisce un set di opzioni di query di sistema che è possibile utilizzare per eseguire operazioni di query tradizionali sulle risorse, quali filtro, ordinamento e paging. Ad esempio, l'URI seguente restituisce il set di tutte le `Order` entità, insieme alle entità `Order_Detail` correlate, i codici postali di `100`che non terminano con:  
  
```http  
https://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')&$expand=Order_Details&$orderby=ShipCity  
```  
  
 Le voci del feed restituito vengono inoltre ordinate in base al valore della proprietà ShipCity degli ordini.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]supporta le opzioni [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] di query di sistema seguenti:  
  
|Opzione query|Descrizione|  
|------------------|-----------------|  
|`$orderby`|Definisce un tipo di ordinamento predefinito per le entità del feed restituito. Nella query seguente il feed restituito dei clienti viene ordinato in base al paese e alla città:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$orderby=Country,City`<br /><br /> Per ulteriori informazioni, vedere [OData: Opzione di query di sistema OrderBy (](https://go.microsoft.com/fwlink/?LinkId=186968)$OrderBy).|  
|`$top`|Specifica il numero di entità da includere nel feed restituito. Nell'esempio seguente vengono ignorati i primi 10 clienti, quindi vengono restituiti i successivi 10:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Per ulteriori informazioni, vedere [OData: Opzione di query di sistema superiore (](https://go.microsoft.com/fwlink/?LinkId=186969)$Top).|  
|`$skip`|Specifica il numero di entità da ignorare prima di avviare la restituzione delle entità nel feed. Nell'esempio seguente vengono ignorati i primi 10 clienti, quindi vengono restituiti i successivi 10:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> Per ulteriori informazioni, vedere [OData: Opzione di query di sistema Skip (](https://go.microsoft.com/fwlink/?LinkId=186971)$Skip).|  
|`$filter`|Definisce un'espressione che filtra le entità restituite nel feed in base a criteri specifici. Questa opzione query supporta un set di operatori di confronto logici, di operatori aritmetici e di funzioni di query predefinite che consentono di valutare l'espressione di filtro. Nell'esempio seguente vengono restituiti tutti gli ordini in cui i codici di avviamento postale non terminano con 100:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')`<br /><br /> Per ulteriori informazioni, vedere [OData: Opzione di query del sistema di filtro](https://go.microsoft.com/fwlink/?LinkId=186972)($Filter).|  
|`$expand`|Specifica quali entità correlate vengono restituite dalla query. Le entità correlate vengono incluse come feed o voce inline con l'entità restituita dalla query. Nell'esempio seguente viene restituito l'ordine per il cliente "ALFKI" insieme ai dettagli relativi agli elementi di ogni ordine:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$expand=Order_Details`<br /><br /> Per ulteriori informazioni, vedere [OData: Espandere l'opzione query di sistema (](https://go.microsoft.com/fwlink/?LinkId=186973)$Expand).|  
|`$select`|Indica che le proprietà dell'entità devono essere restituite nella proiezione. Per impostazione predefinita, tutte le proprietà di un'entità vengono restituite in un feed. Nella query seguente vengono restituite solo tre proprietà dell'entità `Customer`:<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$select=CustomerID,CompanyName,City`<br /><br /> Per ulteriori informazioni, vedere [OData: Selezionare l'opzione query di sistema (](https://go.microsoft.com/fwlink/?LinkID=186076)$Select).|  
|`$inlinecount`|Richiede l'inclusione nel feed di un conteggio del numero di entità restituite nel feed stesso. Per ulteriori informazioni, vedere [OData: Opzione di query di sistema inlinecount (](https://go.microsoft.com/fwlink/?LinkId=186975)$inlinecount).|  
  
## <a name="addressing-relationships"></a>Indirizzamento delle relazioni  
 Oltre ad affrontare i set di entità e le istanze [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] di entità, consente inoltre di indirizzare le associazioni che rappresentano le relazioni tra entità. Questa funzionalità è necessaria per creare o modificare una relazione tra due istanze di entità, ad esempio lo spedizioniere correlato a un determinato ordine nel database Northwind di esempio. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]supporta un `$link` operatore per indirizzare in modo specifico le associazioni tra entità. L'URI seguente viene ad esempio specificato in un messaggio di richiesta PUT HTTP per modificare lo spedizioniere per l'ordine specificato in un nuovo spedizioniere.  
  
```http 
https://services.odata.org/Northwind/Northwind.svc/Orders(10643)/$links/Shipper  
```  
  
 Per ulteriori informazioni, vedere [OData: Indirizzamento di collegamenti](https://go.microsoft.com/fwlink/?LinkId=187351)tra voci.  
  
## <a name="consuming-the-returned-feed"></a>Utilizzo del feed restituito  
 L'URI di una [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] risorsa consente di indirizzare i dati di entità esposti dal servizio. Quando si immette un URI nel campo dell'indirizzo di una Web browser, viene [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] restituita una rappresentazione del feed della risorsa richiesta. Per ulteriori informazioni, vedere la [Guida introduttiva WCF Data Services](quickstart-wcf-data-services.md). Anche se un Web browser può essere utile per verificare che una risorsa del servizio dati restituisca i dati previsti, i servizi dati di produzione che possono anche creare, aggiornare ed eliminare dati vengono in genere accessibili dal codice dell'applicazione o dai linguaggi di script in una pagina Web. Per ulteriori informazioni, vedere [utilizzo di un servizio dati in un'applicazione client](using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Sito Web Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=182204)
