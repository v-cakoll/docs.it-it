---
title: Verifica Get e Put condizionale
ms.date: 03/30/2017
ms.assetid: 3d22067f-57b8-4e0f-a571-a694512187ae
ms.openlocfilehash: f2d170da80de1186aa41b4821da52d58a0bb0e0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33505730"
---
# <a name="conditional-get-and-put"></a>Verifica Get e Put condizionale
In questo esempio viene descritto come utilizzare le nuove API di aggiornamento e recupero condizionali per il modello di programmazione WCF REST. Poiché sono più appropriati per recuperare condizionale e aggiornare orientato alle risorse e i servizi REST, in questo esempio estende la [servizio risorse di base](../../../../docs/framework/wcf/samples/basic-resource-service.md) esempio. Questo esempio si concentra sull'aggiunta di supporto per recupero condizionali e l'aggiornamento per il [servizio risorse di base](../../../../docs/framework/wcf/samples/basic-resource-service.md) di esempio utilizzando le nuove API introdotta in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].  
  
## <a name="demonstrates"></a>Dimostrazione  
 Aggiornamento e recupero condizionali  
  
## <a name="discussion"></a>Discussione  
 In questo esempio, il servizio WCF presenta una raccolta di clienti in modo REST e orientato alle risorse. Per una descrizione dettagliata dell'implementazione del servizio, vedere il [servizio risorse di base](../../../../docs/framework/wcf/samples/basic-resource-service.md) esempio.  
  
 Questo esempio aggiunge funzionalità di aggiornamento per e recupero condizionali di [servizio risorse di base](../../../../docs/framework/wcf/samples/basic-resource-service.md) esempio. Aggiornamento e recupero condizionali utilizzano tag di entità HTTP e le intestazioni HTTP If-None-Match e If-Match per convalidare il fatto che i client dispongano o meno dell'entità più aggiornata per una determinata risorsa. Tuttavia, l'attività di implementazione di codice per analizzare correttamente le intestazioni HTTP If-None-Match e If-Match può essere monotona e soggetta ad errori. Pertanto, i metodi <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> e <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> sono stati aggiunti a <xref:System.ServiceModel.Web.IncomingWebRequestContext>, a cui è possibile accedere utilizzando l'istanza corrente di <xref:System.ServiceModel.Web.WebOperationContext>. Inoltre, il metodo `SetETag` è stato aggiunto a <xref:System.ServiceModel.Web.OutgoingWebRequestContext>, semplificando la restituzione di tag di entità validi.  
  
 Il metodo <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> deve essere utilizzato con operazioni [WebGet]. Il tag di entità corrente per la risorsa specificata viene considerato come parametro `entityTag`, che può essere di tipo `string`, `int`, `long` o `Guid`. Il metodo <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> verifica il tag di entità nell'intestazione HTTP If-None-Match della richiesta. Se il tag di entità è presente nell'intestazione HTTP If-None-Match, viene generata un'eccezione <xref:System.ServiceModel.Web.WebFaultException> con il codice di stato Non modificato (304); in caso contrario, il metodo termina. Il meccanismo di recupero condizionale consente al client di indicare al server che dispone di tale entità e di inviare l'entità corrente solo se il client ne è sprovvisto. È possibile visualizzare l'utilizzo di esempio del metodo <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> nelle operazioni `GetCustomer` e `GetCustomers` del servizio. È importante notare che le chiamate a <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> potrebbero non restituire alcun risultato. Gli sviluppatori devono implementare l'operazione in modo tale che sia possibile determinare l'esito positivo della richiesta prima che venga eseguita la chiamata a <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>. In mancanza della chiamata a <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>, il servizio invierebbe in questo modo una risposta con un codice di stato che indica un esito positivo.  
  
 Il metodo <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> è analogo al metodo <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>. Il tag di entità corrente viene utilizzato anche per la risorsa specificata. Tuttavia, deve essere utilizzato con operazioni [WebInvoke] in cui il metodo è impostato su "PUT" o "DELETE". Il metodo <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> verifica il tag di entità nell'intestazione HTTP If-Match della richiesta. Se il tag di entità non è presente nell'intestazione HTTP If-Match, viene generata un'eccezione <xref:System.ServiceModel.Web.WebFaultException> con il codice di stato Precondizione non riuscita (412). Il meccanismo di aggiornamento condizionale consente al client di indicare al server che dispone di tale entità per la risorsa. Consente inoltre solo al client di modificare la risorsa, se l'entità di cui dispone è corrente. È possibile visualizzare l'utilizzo di esempio del metodo <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> nelle operazioni `UpdateCustomer` e `DeleteCustomer` del servizio. In modo analogo a quanto avviene con <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>, è importante notare che le chiamate a <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> potrebbero non restituire alcun risultato. Gli sviluppatori devono implementare l'operazione in modo tale che sia possibile determinare l'esito positivo della richiesta prima che venga eseguita la chiamata a <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>. In mancanza della chiamata a <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A>, il servizio invierebbe in questo modo una risposta con un codice di stato che indica un'esito positivo.  
  
 L'esempio è costituito da un servizio indipendente e da un client in esecuzione in un'applicazione console. Quando l'applicazione console è in esecuzione, il client invia richieste al servizio e scrive nella finestra della console le informazioni pertinenti incluse nelle risposte.  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  Aprire la soluzione per l'esempio relativo alla verifica Get e Put condizionale. Per garantire l'esecuzione corretta dell'esempio, è necessario avviare [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] come amministratore. Farlo facendo clic con il [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icona e scegliendo **Esegui come amministratore** dal menu di scelta rapida.  
  
2.  Premere CTRL+MAIUSC+B per compilare la soluzione, quindi premere CTRL+F5 per eseguire il progetto di applicazione console. Se nell'esecuzione del progetto il debug è abilitato (premendo F5 anziché CTRL+F5), il debugger si arresta quando viene generata un'eccezione dalla verifica GET e PUT condizionale. Quando ciò si verifica, premere F5 per continuare l'esecuzione dell'esempio.  
  
3.  Viene visualizzata la finestra della console, che fornisce l'URI del servizio in esecuzione e l'URI della pagina della Guida HTML per il servizio in esecuzione.  
  
4.  Durante l'esecuzione dell'esempio, il client invia richieste al servizio e scrive le risposte nella finestra della console.  
  
5.  Premere un tasto qualsiasi per terminare l'esempio.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\ConditionalGetAndPut`
