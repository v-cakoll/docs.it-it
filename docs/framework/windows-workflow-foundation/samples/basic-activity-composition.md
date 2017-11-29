---
title: "Composizione dell'attività di base"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f1c94a276cf2e76d595a22c5c930614818bbf2b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="basic-activity-composition"></a>Composizione dell'attività di base
In questo esempio viene illustrato come creare attività personalizzate e attività fornite dal sistema per compilare attività più personalizzate.  
  
 Il flusso di lavoro che usa attività Survey pianifica tale attività con un elenco di domande, quindi restituisce le risposte ricevute.  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 In questo esempio sono usate tre attività personalizzate. `ReadLine`è un semplice <xref:System.Activities.NativeActivity> \<stringa > che crea un <xref:System.Activities.Bookmark> quando pianificato e quindi imposta il `Return` <xref:System.Activities.OutArgument%601> per il valore con cui il <xref:System.Activities.Bookmark> viene ripreso. `Prompt`è un <xref:System.Activities.Activity%601> \<stringa > che accetta un <xref:System.Activities.InArgument%601>< stringa\> denominato `Text` e risposta vengono restituiti gli utenti di `Result` <xref:System.Activities.OutArgument%601> \<stringa >. L'attività `Prompt` usa le attività <xref:System.Activities.Statements.Sequence> e <xref:System.Activities.Statements.WriteLine> che vengono fornite come parte di .NET Framework e inoltre incorpora l'attività `ReadLine` personalizzata per l'acquisizione di input dell'utente. `Survey` è l'ultima attività personalizzata. Si tratta di un <xref:System.Activities.Activity>< ICollection\<stringa >>.  Questa attività accetta un <xref:System.Activities.InArgument%601>< IEnumerable < stringa\>> denominato `Questions` e popolare il `Result` fuori dall'argomento con le risposte. L'attività `Survey` usa gli oggetti <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> e <xref:System.Activities.Statements.AddToCollection%601> da .NET Framework e l'attività `Prompt` per porre le domande del sondaggio e ottenere le risposte.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Aprire il **BasicActivityComposition.sln** soluzione di esempio [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compilare ed eseguire la soluzione.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`  
  
## <a name="see-also"></a>Vedere anche
