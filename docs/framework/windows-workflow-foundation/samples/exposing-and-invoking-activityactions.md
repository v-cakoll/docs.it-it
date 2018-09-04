---
title: Esposizione e richiamo di ActivityAction
ms.date: 03/30/2017
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
ms.openlocfilehash: f36d88fc54e5150927113ed8825fbccad84129d4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520123"
---
# <a name="exposing-and-invoking-activityactions"></a>Esposizione e richiamo di ActivityAction
In questo esempio viene illustrato come sviluppare un'attività personalizzata che dispone di un oggetto <xref:System.Activities.ActivityAction>. Viene inoltre illustrato come usare questa attività fornendo un'implementazione dell'oggetto <xref:System.Activities.ActivityAction>.  
  
 Un <xref:System.Activities.ActivityAction> consente a un autore di attività di esporre "buchi" con le firme specifiche in cui l'utente di attività può collegare un comportamento personalizzato. Ad esempio, il <!--zz <xref:System.Activities.Statements.ForEach>--> `System.Activities.Statements.ForEach` attività (che agisce su una raccolta di elementi,) ha un <xref:System.Activities.ActivityAction> che consente all'utente di attività associare un comportamento che agisce sull'elemento iterazione corrente.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Aprire il **ActivityAction** nella soluzione di esempio [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compilare ed eseguire la soluzione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`