---
title: Esempio di endpoint di gestione del flusso di lavoro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ac6e08f-c43d-4bb7-83c3-e3890a4dac03
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9d13d1d2af449631f93dd4df29ff41113ffbbfec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-management-endpoint-sample"></a>Esempio di endpoint di gestione del flusso di lavoro
In questo esempio viene illustrato come è possibile usare un endpoint di controllo del flusso di lavoro per creare ed eseguire flussi di lavoro sia in modalità locale che remota. Nell'esempio viene illustrato come ospitare un endpoint di controllo e scrivere client che chiamano l'endpoint di controllo per creare ed eseguire l'istanza di un flusso di lavoro. Il flusso di lavoro non è un servizio.  
  
 Sul lato del servizio nell'esempio un flusso di lavoro è ospitato con l'oggetto WorkflowServiceHost e viene aggiunto un oggetto WorkflowControlEndpoint in modo da consentire ai client di eseguire le operazioni di controllo (sospensione, avvio e via di seguito). Viene inoltre aggiunto un oggetto CreationEndpoint definito dall'utente per consentire la creazione del flusso di lavoro. Il servizio usa quindi questi endpoint per avviare il flusso di lavoro in uno stato sospeso per poi riprenderne l'esecuzione. Il client esegue le stesse operazioni ma dal codice client. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]vedere queste interfacce, [Endpoint di controllo di flusso di lavoro](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md) e [procedura: ospitare un flusso di lavoro non di servizio in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  Eseguire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] con privilegi di amministratore.  
  
2.  Aprire la soluzione di esempio ManagementEndpoint.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Per compilare la soluzione, premere CTRL + MAIUSC + B o scegliere **Compila soluzione** dal **compilare** menu.  
  
4.  Avviare l'applicazione ManagementEndpoint.exe.  
  
5.  Avviare l'applicazione Client.exe.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ManagementEndpoint`  
  
## <a name="see-also"></a>Vedere anche
