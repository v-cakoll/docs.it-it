---
title: Correlazione di query del messaggio LINQ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b746872e-57b1-4514-b337-53398a0e0deb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1207f371da5b447903e2846229860fd8c214a46e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="linq-message-query-correlation"></a>Correlazione di query del messaggio LINQ
In questo esempio viene illustrato come eseguire una correlazione basata sul contenuto usando un'implementazione <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizzata anziché l'oggetto <xref:System.ServiceModel.XPathMessageQuery> fornito dal sistema.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Oggetto <xref:System.ServiceModel.Dispatcher.MessageQuery> personalizzato, correlazione basata sul contenuto.  
  
## <a name="discussion"></a>Discussione  
 In questo esempio viene illustrato come estendersi dalla classe base <xref:System.ServiceModel.Dispatcher.MessageQuery> per scopi di correlazione. L'implementazione personalizzata, `LinqMessageQuery`, consente agli utenti di fornire un XName da trovare all'interno del messaggio tramite XLinq. I dati recuperati dalla query vengono usati per formare la chiave di correlazione per l'invio di messaggi all'istanza del flusso di lavoro appropriata.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  In questo esempio viene esposto un servizio flusso di lavoro tramite endpoint HTTP. Eseguire questa procedura elenchi ACL di URL di esempio, appropriata deve essere aggiunto (vedere [Configuring HTTP and HTTPS](http://go.microsoft.com/fwlink/?LinkId=70353) per informazioni dettagliate), eseguendo Visual Studio come amministratore o eseguendo il comando seguente in un prompt dei comandi con privilegi elevati per aggiungere gli ACL appropriati. Assicurarsi che vengono sostituiti il dominio e il nome utente.  
  
    ```  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2.  Una volta aggiunti gli elenchi ACL URL, usare i passaggi seguenti.  
  
    1.  Compilare la soluzione.  
  
    2.  Impostare più progetti di avvio facendo clic sulla soluzione e selezionando **Imposta progetti di avvio**. Aggiungere **servizio** e **Client** (in tale ordine) come più progetti di avvio.  
  
    3.  Eseguire l'applicazione. Nella console client viene illustrato un flusso di lavoro che invia un ordine, riceve l'ID dell'ordine di acquisto e conferma quindi successivamente l'ordine. Nella finestra Servizio verranno visualizzate le richieste elaborate.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\LinqMessageQueryCorrelation`
