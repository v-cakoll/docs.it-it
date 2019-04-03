---
title: Comportamento di debug del servizio
ms.date: 03/30/2017
ms.assetid: 9d8fd3fb-dc39-427a-8235-336a7e7162ba
ms.openlocfilehash: 4eac577775074abf8c5f35c73dfa3286a75c2744
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835773"
---
# <a name="service-debug-behavior"></a>Comportamento di debug del servizio
In questo esempio viene illustrato come configurare le impostazioni del comportamento di debug. L'esempio è basato sul [Guida introduttiva](../../../../docs/framework/wcf/samples/getting-started-sample.md), che implementa il `ICalculator` contratto di servizio. Questo esempio definisce in modo esplicito il comportamento di debug del servizio nel file di configurazione. Questa operazione può essere eseguita anche nel codice in modo imperativo.  
  
 In questo esempio, il client è un'applicazione console (.exe) e il servizio è ospitato da Internet Information Services (IIS).  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Il file Web.config per il server definisce il comportamento di debug del servizio per attivare la pagina della Guida e la gestione delle eccezioni come illustrato nell'esempio seguente.  
  
```xml  
<behaviors>  
     <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
         <!-- WARNING: Setting includeExceptionDetailInFaults = "True" could result in leaking secured server information to the client.-->  
         <!-- Please set this to false when deploying -->  
             <serviceDebug includeExceptionDetailInFaults="True" httpHelpPageEnabled="True"/>  
         </behavior>  
     </serviceBehaviors>  
</behaviors>  
```  
  
 [\<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) è l'elemento di configurazione che consente di modificare le proprietà del comportamento di debug del servizio. L'utente può modificare questo comportamento per raggiungere i seguenti obiettivi:  
  
-   Questo consente al servizio di restituire qualsiasi eccezione che viene generata dal codice dell'applicazione anche se l'eccezione non è dichiarata mediante <xref:System.ServiceModel.FaultContractAttribute>. Per eseguire questa operazione si imposta `includeExceptionDetailInFaults` su `true`. Questa impostazione è utile in caso dell'esecuzione il debug di casi dove il server sta generando un'eccezione imprevista.  
  
    > [!IMPORTANT]
    >  Attivare questa impostazione in un ambiente di produzione può comportare dei rischi. Un'eccezione del server imprevista può avere alcune informazioni che non sono destinate al client, quindi impostare `includeExceptionDetailsInFaults` su `true` potrebbe comportare una perdita di informazioni.  
  
-   Il [ \<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) consente inoltre di abilitare o disabilitare la pagina della Guida. Ogni servizio può esporre facoltativamente una pagina della Guida che contiene informazioni sul servizio incluso l'endpoint ottenere WSDL per il servizio. A tale fine, impostare `httpHelpPageEnabled` su `true`. Consente di restituire la pagina della Guida a una richiesta GET all'indirizzo di base del servizio. È possibile modificare questo indirizzo impostando un altro attributo `httpHelpPageUrl`. L'operazione può essere protetta utilizzando HTTPS anziché HTTP. A tale fine, impostare `httpsHelpPageEnabled` e `httpsHelpPageUrl`.  
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nella finestra della console client. Le prime tre operazioni (di addizione, sottrazione e moltiplicazione) devono essere completate. L'ultima operazione (di divisione) ha esito negativo con un'eccezione di divisione per zero.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito il [monouso procedura di installazione per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\ServiceDebug`  
  
