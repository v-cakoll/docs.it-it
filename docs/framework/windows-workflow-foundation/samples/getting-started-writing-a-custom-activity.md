---
title: Guida introduttiva alla scrittura di un'attività personalizzata
ms.date: 03/30/2017
ms.assetid: 3902f5fa-8a43-4048-8a6a-6b15472f90f0
ms.openlocfilehash: 4d9c140ca230750ca1119b33252b1edb8796d458
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43405228"
---
# <a name="getting-started-writing-a-custom-activity"></a>Guida introduttiva alla scrittura di un'attività personalizzata
In questo esempio viene illustrato come definire una semplice attività personalizzata in XAML. All'attività viene assegnato il nome `Rhyme` e la relativa logica è una sequenza di tre attività <xref:System.Activities.Statements.WriteLine>.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Aprire il **sln** nella soluzione di esempio [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compilare ed eseguire la soluzione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\GettingStarted`