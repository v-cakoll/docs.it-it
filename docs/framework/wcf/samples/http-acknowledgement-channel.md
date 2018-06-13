---
title: Canale di riconoscimento HTTP
ms.date: 03/30/2017
ms.assetid: 469f3056-5ef2-4753-8acf-b574d23d83cf
ms.openlocfilehash: c56b2fbe9d0bac3143ee7d234fd36a75f7b8071c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33502832"
---
# <a name="http-acknowledgement-channel"></a>Canale di riconoscimento HTTP
Il canale di riconoscimento HTTP è un esempio di canale su più livelli in grado di modificare il modello di messaggistica unidirezionale, consentendo a un servizio di riconoscere o rifiutare i messaggi in arrivo anziché inviare automaticamente un riconoscimento al momento della ricezione. Il canale di riconoscimento HTTP consente inoltre al servizio di ritardare il riconoscimento fino a quando non è possibile garantire a livello aziendale che il messaggio verrà elaborato.  
  
## <a name="demonstrates"></a>Dimostrazione  
 <xref:System.ServiceModel.Channels.ReceiveContext>, esempio relativo a un canale su più livelli (canale di riconoscimento HTTP).  
  
## <a name="discussion"></a>Discussione  
 Il canale di riconoscimento HTTP implementa <xref:System.ServiceModel.Channels.ReceiveContext> per determinare la struttura del modello di messaggistica request/reply HTTP, trasformandolo in un modello unidirezionale con riconoscimento ritardato. Usando questo nuovo modello, un servizio può garantire l'elaborazione dei messaggi inviando un riconoscimento sotto forma di codice di stato HTTP di OK (200) senza bloccare il client fino a quando l'elaborazione dei messaggi non è stata completata oppure può inviare un messaggio di errore al client sotto forma di codice di stato HTTP Errore server interno (500). Ad esempio, un servizio può inviare un riconoscimento dopo avere scritto un messaggio in una coda, quindi continuare ad elaborare il messaggio in modo asincrono. In questo scenario, è possibile garantire a un client che i messaggi sono stati elaborati almeno una volta dal servizio, se ha rispedito ogni messaggio fino a ricevere una conferma di riconoscimento dal servizio. È importante notare che, se un servizio richiede una rapida elaborazione asincrona di messaggi in HTTP senza alcuna garanzia di elaborazione dei messaggi, <xref:System.ServiceModel.Channels.OneWayBindingElement> è una scelta più appropriata.  
  
 <xref:System.ServiceModel.Channels.ReceiveContext> viene utilizzato per conservare il messaggio mentre si determina se può essere elaborato a livello di servizio. La capacità di un servizio di elaborare correttamente il messaggio viene indicata con una chiamata del metodo Complete nell'oggetto <xref:System.ServiceModel.Channels.ReceiveContext> che invia un codice di stato HTTP di OK e se il servizio è in grado di elaborare il messaggio viene indicata con una chiamata <xref:System.ServiceModel.Channels.ReceiveContext> al `Abandon` metodo  nell'oggetto <xref:System.ServiceModel.Channels.ReceiveContext>, che invia un codice di stato HTTP Errore interno del server.  
  
 In questo esempio, il client richiede l'elaborazione di informazioni inviando un ID dipendente. Alla fine del servizio, se l'ID dipendente ricevuto è superiore a 50, il servizio restituisce al client un codice di stato HTTP 500 (Errore server interno); in caso contrario, si parte dal presupposto che l'elaborazione possa essere effettuata correttamente e al client viene inviato un codice di stato HTTP 200 (OK).  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Aprire [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] con privilegi di amministratore.  
  
2.  Aprire il **HttpAckChannel** soluzione.  
  
3.  Avviare una nuova istanza di **servizio** progetto facendo clic sul progetto in **Esplora soluzioni**e selezionando **Debug**, **Avvia nuova istanza** dal menu di scelta rapida.  
  
4.  Avviare una nuova istanza di **Client** progetto facendo clic sul progetto in **Esplora soluzioni**e selezionando **Debug**, e **Avvia nuova istanza** dal menu di scelta rapida.  
  
5.  Una volta avviato il servizio, premere INVIO nella finestra del client per consentire al client di inviare un messaggio al servizio.  
  
6.  Il primo messaggio viene elaborato nel servizio e restituisce un codice di stato HTTP di OK al client.  
  
7.  Il secondo messaggio è relativo alla mancata riuscita dell'operazione e restituisce un codice di stato HTTP Errore server interno al client, che genera un'eccezione <xref:System.ServiceModel.CommunicationException> nel client.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpAckChannel`
