---
title: Correlazione di query del messaggio LINQ
ms.date: 03/30/2017
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
ms.openlocfilehash: cc13696cfd8eb2dcdf22fdc067518c8bd55ca32d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59327672"
---
# <a name="linq-message-query-correlation"></a>Correlazione di query del messaggio LINQ
In questo esempio viene illustrato come eseguire una correlazione basata sul contenuto usando un'implementazione <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizzata anziché l'oggetto <xref:System.ServiceModel.XPathMessageQuery> fornito dal sistema.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Oggetto <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizzato, correlazione basata sul contenuto.  
  
## <a name="discussion"></a>Discussione  
 In questo esempio viene illustrato come estendersi dalla classe base <xref:System.ServiceModel.Dispatcher.MessageQuery> per scopi di correlazione. L'implementazione personalizzata, `LinqMessageQuery`, consente agli utenti di fornire un XName da trovare all'interno del messaggio tramite XLinq. I dati recuperati dalla query vengono usati per formare la chiave di correlazione per l'invio di messaggi all'istanza del flusso di lavoro appropriata.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. In questo esempio viene esposto un servizio flusso di lavoro tramite endpoint HTTP. Per eseguire questo esempio, corretto elenchi ACL URL deve essere aggiunto (vedere [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) per informazioni dettagliate), tramite l'esecuzione di Visual Studio come amministratore oppure eseguendo il comando seguente in un prompt dei comandi con privilegi elevati per aggiungere gli ACL appropriati. Assicurarsi che vengono sostituiti il dominio e il nome utente.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. Una volta aggiunti gli elenchi ACL URL, usare i passaggi seguenti.  
  
    1.  Compilare la soluzione.  
  
    2.  Impostare più progetti di avvio facendo clic sulla soluzione e selezionando **Imposta progetti di avvio**. Aggiungere **assistenza** e **Client** (in questo ordine) come più progetti di avvio.  
  
    3.  Eseguire l'applicazione. Nella console client viene illustrato un flusso di lavoro che invia un ordine, riceve l'ID dell'ordine di acquisto e conferma quindi successivamente l'ordine. Nella finestra Servizio verranno visualizzate le richieste elaborate.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
