---
title: Criteri semplici
ms.date: 03/30/2017
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
ms.openlocfilehash: 7f189e4d1811cb0b7dd9138b944bfd0552481690
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43561264"
---
# <a name="simple-policy"></a>Criteri semplici
In questo esempio viene mostrato come usare un'attività <xref:System.Workflow.Activities.PolicyActivity> in un flusso di lavoro.  
  
 Il flusso di lavoro sequenziale in questo esempio viene creato usando un'attività <xref:System.Workflow.Activities.PolicyActivity>. Il flusso di lavoro definisce campi `orderValue`, `customerType` e `discount` usati per definire un flusso di lavoro di sconto del prodotto. Le regole definite nel file delle regole impostano un valore di sconto basato su `orderValue` e `customerType`. `orderValue` e `customerType` sono impostati nella definizione della classe `SimplePolicyWorkflow` e possono essere modificati per modificarne il comportamento. Lo sconto risultante viene scritto nella console nel gestore eventi <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> definito nella classe `SimplePolicyWorkflow`.  
  
### <a name="to-build-the-sample"></a>Per compilare l'esempio  
  
1.  Aprire la soluzione in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Premere CTRL+MAIUSC+B per compilare la soluzione,  
  
3.  Eseguire la soluzione senza debug premendo CTRL+F5.  
  
### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
-   Nella finestra del prompt dei comandi di SDK eseguire il file con estensione exe nella cartella SimplePolicy\bin\debug (oppure nella cartella SimplePolicy\bin per la versione Visual Basic dell'esempio), collocata sotto la cartella principale dell'esempio.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [Criteri avanzati](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
