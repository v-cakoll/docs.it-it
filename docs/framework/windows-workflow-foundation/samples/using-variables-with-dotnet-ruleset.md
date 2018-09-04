---
title: Utilizzo di variabili con un set di regole di .NET Framework 3.5
ms.date: 03/30/2017
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
ms.openlocfilehash: 64d47564076e19e152e30b6ab0cb3900ce53cfa1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512854"
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a>Utilizzo di variabili con un set di regole di .NET Framework 3.5
In questo esempio viene illustrato come creare un flusso di lavoro che usa l'attività <xref:System.Activities.Statements.Interop> per integrare un'attività personalizzata scritta in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] che usa criteri e regole. I dati vengono passati dal flusso di lavoro all'attività personalizzata associando variabili alle proprietà di dipendenza esposte dall'attività personalizzata.  
  
## <a name="sample-walkthrough"></a>Scenario di esempio  
  
#### <a name="to-examine-travelrulelibrary"></a>Per esaminare TravelRuleLibrary  
  
1.  Usa Visual Studio, aprire la soluzione interopwith35ruleset.sln.  
  
2.  Aprire TravelRuleSet.cs nella finestra di progettazione del flusso di lavoro.  
  
     Viene visualizzata un'attività sequenziale personalizzata che contiene <xref:System.Workflow.Activities.PolicyActivity>.  
  
3.  Fare doppio clic sull'attività dei criteri DiscountPolicy per esaminare le regole  
  
     che possono essere visualizzate nel relativo editor.  
  
4.  Fare clic il `DiscountPolicy` e selezionare il **Visualizza codice** possibilità di esaminare il code-beside codice c# per l'attività.  
  
     Osservare l'impostazione della proprietà di dipendenza per l'oggetto `DiscountLevel`. È equivalente agli argomenti in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]. Per altre informazioni sugli argomenti, vedere [variabili e argomenti](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).  
  
## <a name="interopwith35ruleset"></a>InteropWith35RuleSet  
 Si tratta di un progetto di flusso di lavoro sequenziale che usa l'attività <xref:System.Activities.Statements.Interop> per eseguire l'integrazione con il set di regole personalizzato creato nel progetto `TravelRuleLibrary`. Le variabili vengono create nell'attività <xref:System.Activities.Statements.Sequence> di primo livello. L'attività <xref:System.Activities.Statements.Interop> viene usata per eseguire l'integrazione con l'attività `TravelRuleSet`. Le variabili dichiarate nell'oggetto <xref:System.Activities.Statements.Sequence> vengono usate per eseguire l'associazione alle proprietà di dipendenza.  
  
## <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione InteropWith35RuleSet.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`