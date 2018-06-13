---
title: Operazioni asincrone (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
- WCF Data Services, client library
ms.assetid: 679644c7-e3fc-422c-b14a-b44b683900d0
ms.openlocfilehash: f2f1ef1f4915faf8cfd7bd5a561cf7dbd3645df7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365917"
---
# <a name="asynchronous-operations-wcf-data-services"></a>Operazioni asincrone (WCF Data Services)
Le applicazioni Web devono includere una latenza tra client e server superiore a quella delle applicazioni eseguite in reti interne. Per ottimizzare le prestazioni e l'esperienza utente dell'applicazione, si consiglia di usare i metodi asincroni delle classi <xref:System.Data.Services.Client.DataServiceContext> e <xref:System.Data.Services.Client.DataServiceQuery%601> in caso di accesso ai server di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] sul Web.  
  
 Sebbene i server di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] elaborino le richieste HTTP in modo asincrono, alcuni metodi delle librerie client di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] sono sincroni e attendono il completamento dell'intero scambio richiesta-risposta prima di continuare l'esecuzione. I metodi asincroni delle librerie client di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] non attendono il completamento di questo scambio e consentono all'applicazione di mantenere nel frattempo il livello di risposta di un'interfaccia utente.  
  
 È possibile eseguire le operazioni asincrone utilizzando una coppia di metodi sul <xref:System.Data.Services.Client.DataServiceContext> e <xref:System.Data.Services.Client.DataServiceQuery%601> classi che iniziano con *iniziare* e *fine* rispettivamente. Il *iniziare* metodi registrano un delegato che il servizio viene chiamato quando l'operazione è stata completata. Il *fine* metodi devono essere chiamati nel delegato registrato per gestire il callback dalle operazioni completate. Quando si chiama il *fine* metodo per completare un'operazione asincrona, è necessario eseguire questa operazione dalla stessa <xref:System.Data.Services.Client.DataServiceQuery%601> o <xref:System.Data.Services.Client.DataServiceContext> istanza utilizzato per avviare l'operazione. Ogni *iniziare* metodo accetta un `state` parametro che è possibile passare un oggetto di stato al callback. Questo oggetto stato viene recuperato dal <xref:System.IAsyncResult> che viene fornito con il callback e viene utilizzata per chiamare il corrispondente *fine* metodo per completare l'operazione asincrona. Ad esempio, quando si fornisce l'istanza di <xref:System.Data.Services.Client.DataServiceQuery%601> come parametro `state` durante la chiamata del metodo <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> sull'istanza, la stessa istanza di <xref:System.Data.Services.Client.DataServiceQuery%601> viene restituita da <xref:System.IAsyncResult>. Questa istanza di <xref:System.Data.Services.Client.DataServiceQuery%601> viene quindi usata per chiamare il metodo <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> per completare l'operazione di query. Per ulteriori informazioni, vedere [procedura: eseguire query sul servizio di dati asincrono](../../../../docs/framework/data/wcf/how-to-execute-asynchronous-data-service-queries-wcf-data-services.md).  
  
> [!NOTE]
>  Solo le operazioni asincrone sono supportate dalle librerie client fornite in .NET Framework per Silverlight. Per ulteriori informazioni, vedere [WCF Data Services (Silverlight)](http://go.microsoft.com/fwlink/?LinkID=143149).  
  
 Le librerie client di .NET Framework supportano le operazioni asincrone seguenti:  
  
|Operazione|Metodi|  
|---------------|-------------|  
|Esecuzione di un oggetto <xref:System.Data.Services.Client.DataServiceQuery%601>.|-   <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>|  
|Esecuzione di una query dall'oggetto <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecute%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecute%2A>|  
|Esecuzione di una query batch dall'oggetto <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginExecuteBatch%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndExecuteBatch%2A>|  
|Caricamento di un'entità correlata nell'oggetto <xref:System.Data.Services.Client.DataServiceContext>.|-   <xref:System.Data.Services.Client.DataServiceContext.BeginLoadProperty%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndLoadProperty%2A>|  
|Salvataggio di modifiche nell'oggetto <xref:System.Data.Services.Client.DataServiceContext>|-   <xref:System.Data.Services.Client.DataServiceContext.BeginSaveChanges%2A><br />-   <xref:System.Data.Services.Client.DataServiceContext.EndSaveChanges%2A>|  
  
## <a name="threading-considerations-for-asynchronous-operations"></a>Considerazioni sul threading per operazioni asincrone  
 In un'applicazione a thread multipli, che viene registrato come un callback per l'operazione asincrona viene richiamato il delegato non necessariamente sullo stesso thread che è stato utilizzato per chiamare il *iniziare* metodo, che crea la richiesta iniziale. In un'applicazione in cui il callback deve essere richiamato su un thread specifico, è necessario effettuare il marshalling esplicito l'esecuzione del *fine* metodo che gestisce la risposta, al thread desiderato. Nelle applicazioni basate su Windows Presentation Foundation (WPF) e su Silverlight è ad esempio necessario che il marshalling della risposta venga effettuato di nuovo al thread dell'interfaccia utente usando il metodo <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> sull'oggetto <xref:System.Windows.Threading.Dispatcher>. Per ulteriori informazioni, vedere [l'esecuzione di query del servizio dati (WCF Data Services/Silverlight)](http://msdn.microsoft.com/library/3a7cdc07-c37e-4da2-b98b-c3763fd0970b).  
  
## <a name="see-also"></a>Vedere anche  
 [Libreria client WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
