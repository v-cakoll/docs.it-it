---
title: Utilizzo della classe WorkflowInvoker
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 553367916ff249118a8fcdd8273382402b90cfcc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-workflowinvoker-class"></a>Utilizzo della classe WorkflowInvoker
In questo esempio viene illustrato come usare la classe <xref:System.Activities.WorkflowInvoker> per richiamare un'attività come se fosse un metodo.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 L'uso della classe <xref:System.Activities.WorkflowInvoker> è il modo più semplice per eseguire un'attività. È progettata per eseguire direttamente un'attività come una chiamata al metodo. Questa API ad alte prestazioni, leggera e semplice da usare in scenari in cui l'esecuzione di un'attività non richiede l'infrastruttura di controllo fornita da altre varianti di hosting.  
  
 L'esempio utilizza un'attività personalizzata che deriva da <xref:System.Activities.CodeActivity%601>< Int32\> denominato `Add` che aggiunge due <xref:System.Activities.InArgument%601>, `X` e `Y`e restituisce un `Result` <xref:System.Activities.OutArgument%601>. (<xref:System.Activities.CodeActivity%601>\<T > deriva da <xref:System.Activities.Activity%601>< T\>, che presenta un <xref:System.Activities.OutArgument%601> \<T > denominato `Result`.) Oggetto `Dictionary` \<stringa, oggetto > viene utilizzato per passare argomenti a un'attività richiamata tramite <xref:System.Activities.WorkflowInvoker>. La chiave del dizionario corrisponde al nome di un argomento nell'attività richiamata. Il valore associato a una particolare chiave viene associato all'argomento identificato dalla chiave.  
  
 Nell'esempio viene chiamato <xref:System.Activities.WorkflowInvoker.Invoke%2A> e viene passato un dizionario che contiene valori per `X` e `Y`. La classe <xref:System.Activities.WorkflowInvoker> associa questi valori agli argomenti dell'attività `Add`, esegue l'attività e restituisce il risultato.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione Invoker.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`