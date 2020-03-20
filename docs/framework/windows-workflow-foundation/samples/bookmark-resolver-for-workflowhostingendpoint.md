---
title: Risolver di segnalibri per WorkflowHostingEndpoint
ms.date: 03/30/2017
ms.assetid: 97fd5816-935e-4625-ad04-e6f6befa07de
ms.openlocfilehash: 113e6e52214d482dcd733bbd07ef2aab9f1b8c3f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142810"
---
# <a name="bookmark-resolver-for-workflowhostingendpoint"></a>Risolver di segnalibri per WorkflowHostingEndpoint
In questo esempio viene illustrato come usare l'oggetto <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> con l'oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost> per creare istanze del flusso di lavoro.  
  
## <a name="demonstrates"></a>Dimostra  
 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
## <a name="discussion"></a>Discussione  
 In questo esempio viene usato <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> per creare istanze del flusso di lavoro ospitate usando <xref:System.ServiceModel.Activities.WorkflowServiceHost>. <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> è un punto di estensibilità per <xref:System.ServiceModel.Activities.WorkflowServiceHost> che può essere usato negli scenari seguenti:  
  
- Creazione di nuove istanze del flusso di lavoro.  
  
- Ripresa di segnalibri nell'istanza del flusso di lavoro ospitata in un oggetto <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  
  
 L'endpoint di esempio incluso espone un contratto che fornisce operazioni per creare un flusso di lavoro e restituisce l'ID istanza o crea un'istanza con un ID specifico. L'applicazione console di esempio crea un'istanza <xref:System.ServiceModel.Activities.WorkflowServiceHost> con una definizione di flusso di lavoro e aggiunge un oggetto `CreationEndpoint` all'host. Successivamente chiama l'operazione `Create` nell'endpoint per creare una nuova istanza del flusso di lavoro.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Compilare la soluzione.  
  
2. Eseguire l'applicazione. Nella console `CreationEndpoint` viene visualizzato un messaggio che include l'ID istanza quando viene creata l'istanza del flusso di lavoro. Il messaggio "Hello World!" stampa dall'istanza del flusso di lavoro.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreationEndpoint`
