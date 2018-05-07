---
title: Selezione automatica del formato
ms.date: 03/30/2017
ms.assetid: dab51e56-8517-4a6a-bb54-b55b15ab37bb
ms.openlocfilehash: 9b9b4da4d5d3bdb3892feb49c033fbe4fc640cb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="automatic-format-selection"></a>Selezione automatica del formato
In questo esempio viene illustrato come abilitare la selezione automatica del formato (XML o JSON) con il modello, nonché come impostare in modo esplicito il formato nel codice dell'operazione di programmazione REST di Windows Communication Foundation (WCF).  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 L'esempio è costituito da un servizio e dal codice client che effettua le richieste al servizio. Il servizio supporta una singola operazione `GET` (`EchoWithGet`) HTTP e una singola operazione `POST` (`EchoWithPost`) HTTP. Entrambe operazioni prevedono una stringa, quindi restituiscono la stringa nella risposta. Con l'operazione `GET`, la stringa viene fornita in un parametro della stringa di query dell'URI. Con l'operazione `POST`, la stringa viene fornita nel corpo della richiesta serializzata in XML. Il servizio è in grado di restituire risposte in XML o JSON usando le nuove funzionalità di selezione automatica del formato e di selezione imperativa del formato di [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].  
  
 Nell'esempio la selezione automatica del formato viene abilitata tramite il file App.config. Sull'endpoint HTTP Web predefinito all'attributo `automaticFormatSelectionEnabled` è stato assegnato il valore `true`. Con la selezione automatica del formato abilitata, l'infrastruttura di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] seleziona il formato di riposta più appropriato (XML o JSON) analizzando le intestazioni HTTP Accept e Content-Type della richiesta. Per usare questa nuova funzionalità, non è necessario che lo sviluppatore fornisca una configurazione o un codice aggiuntivo oltre all'impostazione dell'attributo `automaticFormatSelectionEnabled` su `true`. Nel codice client in Program.cs le richieste vengono inviate in entrambe le `GET` e `POST` operazioni del servizio con l'intestazione HTTP Accept specificata come "application/xml" o "application/json" e il servizio restituisce una risposta che formato corrispondente.  
  
 Anche nell'operazione `GET` viene usata la selezione imperativa del formato. L'operazione `GET` verifica se è presente un parametro della stringa di query `format` facoltativo e in caso affermativo imposta il formato della risposta sulla proprietà <xref:System.ServiceModel.Web.WebOperationContext.OutgoingResponse%2A>. In questo modo, l'impostazione imperativa del formato della risposta determina l'override della selezione automatica del formato effettuata dall'infrastruttura di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 L'esempio è costituito da un servizio indipendente e da un client in esecuzione in un'applicazione console. Quando l'applicazione console è in esecuzione, il client invia richieste al servizio e scrive nella finestra della console le informazioni pertinenti incluse nelle risposte.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire la soluzione per l'esempio relativo alla selezione automatica del formato. Per garantire l'esecuzione corretta dell'esempio, è necessario che l'avvio di [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] venga eseguito come amministratore. Farlo facendo clic con il [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] sull'icona e selezionare **Esegui come amministratore** dal menu di scelta rapida.  
  
2.  Premere CTRL+MAIUSC+B per compilare la soluzione, quindi premere CTRL+F5 per eseguire il progetto AutomaticFormatSelection dell'applicazione console. Verrà visualizzata la finestra della console in cui saranno disponibili gli URI del servizio in esecuzione e della pagina della Guida HTML per il servizio in esecuzione.  
  
3.  Durante l'esecuzione dell'esempio, il client invia richieste al servizio e scrive le risposte nella finestra della console. Si notino i formati diversi delle risposte in XML e JSON.  
  
4.  Premere un tasto qualsiasi per terminare l'esempio.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AutomaticFormatSelection`  
  
## <a name="see-also"></a>Vedere anche
