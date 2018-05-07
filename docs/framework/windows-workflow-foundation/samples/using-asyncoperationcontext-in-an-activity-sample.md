---
title: Utilizzo di AsyncOperationContext in un esempio di attività
ms.date: 03/30/2017
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
ms.openlocfilehash: da7b62ef9e29621d1e6ee1046afb5455af1164bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="using-asyncoperationcontext-in-an-activity-sample"></a>Utilizzo di AsyncOperationContext in un esempio di attività
In questo esempio viene dimostrato come sviluppare un oggetto <xref:System.Activities.CodeActivity> personalizzato che usa <xref:System.Activities.AsyncCodeActivityContext> per eseguire operazioni asincrone al di fuori del flusso di lavoro.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 L'attività di esempio usa i metodi <xref:System.IO.FileStream.BeginWrite%2A> e <xref:System.IO.FileStream.EndWrite%2A> nella classe <xref:System.IO.FileStream> per scrivere in modo asincrono dati in un file. Il modello introdotto qui può essere adattato per l'uso con gli altri metodi asincroni. Mentre l'operazione asincrona è in esecuzione, possono essere eseguite le altre attività nel flusso di lavoro, ma il flusso di lavoro non può essere salvato in modo permanente.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Aprire la soluzione di esempio Async.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compilare ed eseguire la soluzione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`