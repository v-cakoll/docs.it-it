---
title: Esposizione e richiamo di ActivityAction
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4285718ef1829e9432957278d5ca7959e32e4511
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="exposing-and-invoking-activityactions"></a>Esposizione e richiamo di ActivityAction
In questo esempio viene illustrato come sviluppare un'attività personalizzata che dispone di un oggetto <xref:System.Activities.ActivityAction>. Viene inoltre illustrato come usare questa attività fornendo un'implementazione dell'oggetto <xref:System.Activities.ActivityAction>.  
  
 Un <xref:System.Activities.ActivityAction> consente all'autore di attività di esporre "problemi di sicurezza" con firme specifiche in cui l'utente di attività può associare un comportamento personalizzato. Ad esempio, il <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` attività (che agisce su una raccolta di elementi) dispone di un <xref:System.Activities.ActivityAction> che consente all'utente di attività associare un comportamento che agisce sull'elemento di iterazione corrente.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Aprire il **ActivityAction.sln** soluzione di esempio [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compilare ed eseguire la soluzione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`