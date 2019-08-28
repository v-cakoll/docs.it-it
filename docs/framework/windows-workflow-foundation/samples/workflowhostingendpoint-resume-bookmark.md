---
title: Segnalibro di ripresa WorkflowHostingEndpoint
ms.date: 03/30/2017
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
ms.openlocfilehash: 83065a0034303dcbc83f846ba455f71e954fdb54
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70037771"
---
# <a name="workflowhostingendpoint-resume-bookmark"></a>Segnalibro di ripresa WorkflowHostingEndpoint
In questo esempio viene illustrato come usare l'oggetto <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> con l'oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost> per creare istanze del flusso di lavoro.  
  
## <a name="demonstrates"></a>Dimostrazione  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## <a name="discussion"></a>Discussione  
 In questo esempio viene usato <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> per creare un'istanza del flusso di lavoro ospitata usando <xref:System.ServiceModel.Activities.WorkflowServiceHost>. <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> è un punto di estensibilità per <xref:System.ServiceModel.Activities.WorkflowServiceHost> che può essere usato negli scenari seguenti:  
  
- Creazione di nuove istanze del flusso di lavoro.  
  
- Ripresa di segnalibri in un'istanza del flusso di lavoro ospitata in un oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
 L'endpoint di esempio incluso espone un contratto che fornisce operazioni per creare un flusso di lavoro e restituire l'ID istanza o per creare un'istanza con un ID specifico. L'applicazione console di esempio crea un'istanza <xref:System.ServiceModel.Activities.WorkflowServiceHost> con una definizione di flusso di lavoro di base e aggiunge un oggetto `CreationEndpoint` all'host. Successivamente chiama l'operazione `Create` nell'endpoint per creare una nuova istanza del flusso di lavoro.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Compilare la soluzione.  
  
2. Eseguire l'applicazione. Nella console `CreationEndpoint` viene visualizzato un messaggio che include l'ID istanza quando viene creata l'istanza del flusso di lavoro. Messaggio "Hello World!" viene stampato dal flusso di lavoro al completamento della ripresa del segnalibro.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`
