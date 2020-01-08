---
title: Operazioni asincrone (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
- WCF Data Services, client library
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
ms.openlocfilehash: 5191f3d03facaafc64f6df494ff90cd0ce1c1988
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346187"
---
# <a name="asynchronous-operations-wcf-data-services"></a>Operazioni asincrone (WCF Data Services)
Le applicazioni Web devono includere una latenza tra client e server superiore a quella delle applicazioni eseguite in reti interne. Per ottimizzare le prestazioni e l'esperienza utente dell'applicazione, è consigliabile utilizzare i metodi asincroni delle classi <xref:System.Data.Services.Client.DataServiceContext> e <xref:System.Data.Services.Client.DataServiceQuery%601> per l'accesso ai server WCF Data Services sul Web.  
  
 Anche se i server WCF Data Services elaborano richieste HTTP in modo asincrono, alcuni metodi delle librerie client WCF Data Services sono sincroni e attendono il completamento dell'intero scambio di richiesta-risposta prima di continuare l'esecuzione. I metodi asincroni delle librerie client di WCF Data Services non attendono il completamento di questo scambio e possono consentire all'applicazione di mantenere nel frattempo un'interfaccia utente reattiva.  
  
 È possibile eseguire operazioni asincrone tramite una coppia di metodi sulle classi <xref:System.Data.Services.Client.DataServiceContext> e <xref:System.Data.Services.Client.DataServiceQuery%601> che iniziano rispettivamente con *Begin* e *end* . I metodi *Begin* registrano un delegato chiamato dal servizio al completamento dell'operazione. I metodi *end* devono essere chiamati nel delegato registrato per gestire il callback dalle operazioni completate. Quando si chiama il metodo *end* per completare un'operazione asincrona, è necessario eseguire questa operazione dalla stessa <xref:System.Data.Services.Client.DataServiceQuery%601> o <xref:System.Data.Services.Client.DataServiceContext> istanza usata per avviare l'operazione. Ogni metodo *Begin* accetta un parametro `state` che può passare un oggetto di stato al callback. Questo oggetto di stato viene recuperato dal <xref:System.IAsyncResult> fornito con il callback e viene utilizzato per chiamare il metodo *end* corrispondente per completare l'operazione asincrona. Ad esempio, quando si fornisce l'istanza di <xref:System.Data.Services.Client.DataServiceQuery%601> come parametro `state` durante la chiamata del metodo <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> sull'istanza, la stessa istanza di <xref:System.Data.Services.Client.DataServiceQuery%601> viene restituita da <xref:System.IAsyncResult>. Questa istanza di <xref:System.Data.Services.Client.DataServiceQuery%601> viene quindi usata per chiamare il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> per completare l'operazione di query. Per altre informazioni, vedere [procedura: eseguire query asincrone sul servizio dati](how-to-execute-asynchronous-data-service-queries-wcf-data-services.md).  
  
> [!NOTE]
> Solo le operazioni asincrone sono supportate dalle librerie client fornite in .NET Framework per Silverlight. Per ulteriori informazioni, vedere [WCF Data Services (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)).  
  
 Le librerie client di .NET Framework supportano le operazioni asincrone seguenti:  
  
|Operazione|Metodi|  
|---------------|-------------|  
|Esecuzione di un oggetto <xref:System.Data.Services.Client.DataServiceQuery%601>.|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|Esecuzione di una query dall'oggetto <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|Esecuzione di una query batch dall'oggetto <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|Caricamento di un'entità correlata nell'oggetto <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|Salvataggio di modifiche nell'oggetto <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## <a name="threading-considerations-for-asynchronous-operations"></a>Considerazioni sul threading per operazioni asincrone  
 In un'applicazione multithread il delegato registrato come callback per l'operazione asincrona non viene richiamato necessariamente sullo stesso thread usato per chiamare il metodo *Begin* , che crea la richiesta iniziale. In un'applicazione in cui il callback deve essere richiamato su un thread specifico, è necessario effettuare il marshalling in modo esplicito dell'esecuzione del metodo *end* , che gestisce la risposta, al thread desiderato. Nelle applicazioni basate su Windows Presentation Foundation (WPF) e su Silverlight è ad esempio necessario che il marshalling della risposta venga effettuato di nuovo al thread dell'interfaccia utente usando il metodo <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> sull'oggetto <xref:System.Windows.Threading.Dispatcher>. Per ulteriori informazioni, vedere [esecuzione di query sul servizio dati (WCF Data Services/Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc903932(v=vs.95)).  
  
## <a name="see-also"></a>Vedere anche

- [Libreria client WCF Data Services](wcf-data-services-client-library.md)
