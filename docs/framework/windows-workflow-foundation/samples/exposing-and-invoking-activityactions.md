---
title: Esposizione e richiamo di ActivityAction
ms.date: 03/30/2017
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
ms.openlocfilehash: 2d369ec4b028b047ce02016dd511c1c088b46a91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513152"
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
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`