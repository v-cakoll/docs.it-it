---
title: Utilizzo dell'attività Pick
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: 193b60bff7b08c0de9a0957668483eb73be97274
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43452606"
---
# <a name="using-the-pick-activity"></a>Utilizzo dell'attività Pick
In questo esempio viene illustrato come usare l'attività <xref:System.Activities.Statements.Pick>.  
  
 L'attività <xref:System.Activities.Statements.Pick> fornisce il modello di controllo basato sugli eventi il cui comportamento è analogo a quello dell'istruzione C# `switch`, che esegue solo uno dei rami nell'istruzione `switch`. A differenza dell'istruzione `switch` in cui l'esecuzione di un ramo viene effettuata in base a un valore, l'attività <xref:System.Activities.Statements.Pick> esegue un ramo in base alla modalità di completamento di un'attività.  
  
 In questo esempio un utente deve digitare il nome nella console entro un periodo di tempo specificato. L'attività <xref:System.Activities.Statements.Pick> nell'esempio dispone di due rami eseguiti in base al fatto che l'utente abbia o meno digitato il nome entro 5 secondi. Se l'utente digita il nome nei 5 secondi, viene eseguito il primo ramo che contiene un'attività `ReadLine` personalizzata; in caso contrario, viene eseguito l'altro ramo che contiene un'attività <xref:System.Activities.Statements.Delay>. Una volta digitato nella console, il nome dell'utente viene stampato nella console. Se un input non viene immesso entro 5 secondi, l'operazione è scaduta.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Attività <xref:System.Activities.Statements.Pick>  
  
## <a name="discussion"></a>Discussione  
 Nell'esempio è incluso un flusso di lavoro della finestra di progettazione e un flusso di lavoro codificato.  
  
 Flusso di lavoro della finestra di progettazione  
 Nella versione della finestra di progettazione dell'esempio viene illustrato come creare un flusso di lavoro nella finestra di progettazione. Sono inclusi i file seguenti:  
  
-   Program.cs: include la funzione `Main` che esegue il flusso di lavoro di esempio.  
  
-   ReadString.cs: attività personalizzata che legge alcuni input dalla console.  
  
-   Sequence1.xaml: flusso di lavoro creato tramite la finestra di progettazione usata da Pick.  
  
 Flusso di lavoro codificato  
 Nella versione codificata dell'esempio viene illustrato come creare un flusso di lavoro nella finestra di progettazione. Sono inclusi i file seguenti:  
  
-   Program.cs: include la funzione `Main` che esegue il flusso di lavoro di esempio.  
  
-   ReadString.cs: attività personalizzata che legge alcuni input dalla console.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione Pick.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`