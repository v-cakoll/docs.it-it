---
title: Composizione dell'attività di base
ms.date: 03/30/2017
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
ms.openlocfilehash: ade8187ca44a8182b55cf0f01e5bfe5a9a747255
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518376"
---
# <a name="basic-activity-composition"></a>Composizione dell'attività di base
In questo esempio viene illustrato come creare attività personalizzate e attività fornite dal sistema per compilare attività più personalizzate.  
  
 Il flusso di lavoro che usa attività Survey pianifica tale attività con un elenco di domande, quindi restituisce le risposte ricevute.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 In questo esempio sono usate tre attività personalizzate. `ReadLine` è un semplice <xref:System.Activities.NativeActivity> \<stringa > che consente di creare un <xref:System.Activities.Bookmark> quando pianificato e quindi imposta la `Return` <xref:System.Activities.OutArgument%601> sul valore con cui il <xref:System.Activities.Bookmark> viene ripreso. `Prompt` è un' <xref:System.Activities.Activity%601> \<stringa > che accetta un <xref:System.Activities.InArgument%601>< stringa\> denominato `Text` e restituisce gli utenti di risposta nel `Result` <xref:System.Activities.OutArgument%601> \<string >. L'attività `Prompt` usa le attività <xref:System.Activities.Statements.Sequence> e <xref:System.Activities.Statements.WriteLine> che vengono fornite come parte di .NET Framework e inoltre incorpora l'attività `ReadLine` personalizzata per l'acquisizione di input dell'utente. `Survey` è l'ultima attività personalizzata. Si tratta di un' <xref:System.Activities.Activity>< ICollection\<stringa >>.  Questa attività accetta un <xref:System.Activities.InArgument%601>< IEnumerable < stringa\>> denominato `Questions` e popola la `Result` fuori dall'argomento con le risposte. L'attività `Survey` usa gli oggetti <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> e <xref:System.Activities.Statements.AddToCollection%601> da .NET Framework e l'attività `Prompt` per porre le domande del sondaggio e ottenere le risposte.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Aprire il **Basicactivitycomposition** nella soluzione di esempio [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compilare ed eseguire la soluzione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`