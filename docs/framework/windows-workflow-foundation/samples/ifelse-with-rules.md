---
title: IfElse con regole
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bec818ca5492e9a49a602a4f7baef4b45cb073c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ifelse-with-rules"></a>IfElse con regole
In questo esempio viene mostrato l'uso di una condizione della regola con un'attività <xref:System.Workflow.Activities.IfElseActivity>.  
  
 L'esempio passa un parametro `OrderValue` dall'host. Il valore del parametro viene usato in una condizione della regola sul primo ramo dell'attività <xref:System.Workflow.Activities.IfElseActivity>. Se il valore è minore di 10.000, viene eseguito il primo ramo e <xref:System.Workflow.Activities.CodeActivity> attività nel primo branch stampa **ottenere l'approvazione Manager** nella console. Se il valore è maggiore di 10.000, il <xref:System.Workflow.Activities.CodeActivity> attività nel secondo branch esegue e stampa **ottenere approvazione VP**.  
  
### <a name="to-build-the-sample"></a>Per compilare l'esempio  
  
1.  Aprire la soluzione in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Premere CTRL+MAIUSC+B per compilare la soluzione,  
  
3.  Eseguire la soluzione senza debug premendo CTRL+F5.  
  
### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
-   Nella finestra del prompt dei comandi di SDK eseguire il file con estensione exe nella cartella IfElseWithRules\bin\debug (oppure nella cartella IfElseWithRules\bin per la versione Visual Basic dell'esempio), collocata sotto la cartella principale dell'esempio.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Workflow.Activities.Rules>  
 <xref:System.Workflow.Activities.IfElseActivity>  
 <xref:System.Workflow.Activities.CodeActivity>  
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>
