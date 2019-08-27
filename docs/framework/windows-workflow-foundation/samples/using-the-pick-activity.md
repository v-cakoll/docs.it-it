---
title: Utilizzo dell'attività Pick
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: 03b9ff7f552ad0cdcfbe9c46121a2f46f35de52a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70037873"
---
# <a name="using-the-pick-activity"></a>Utilizzo dell'attività Pick
In questo esempio viene illustrato come usare l'attività <xref:System.Activities.Statements.Pick>.

 L'attività <xref:System.Activities.Statements.Pick> fornisce il modello di controllo basato sugli eventi il cui comportamento è analogo a quello dell'istruzione C# `switch`, che esegue solo uno dei rami nell'istruzione `switch`. A differenza dell'istruzione `switch` in cui l'esecuzione di un ramo viene effettuata in base a un valore, l'attività <xref:System.Activities.Statements.Pick> esegue un ramo in base alla modalità di completamento di un'attività.

 In questo esempio un utente deve digitare il nome nella console entro un periodo di tempo specificato. L'attività <xref:System.Activities.Statements.Pick> nell'esempio dispone di due rami eseguiti in base al fatto che l'utente abbia o meno digitato il nome entro 5 secondi. Se l'utente digita il nome nei 5 secondi, viene eseguito il primo ramo che contiene un'attività `ReadLine` personalizzata; in caso contrario, viene eseguito l'altro ramo che contiene un'attività <xref:System.Activities.Statements.Delay>. Una volta digitato nella console, il nome dell'utente viene stampato nella console. Se un input non viene immesso entro 5 secondi, l'operazione è scaduta.

## <a name="demonstrates"></a>Dimostrazione
 Attività <xref:System.Activities.Statements.Pick>

## <a name="discussion"></a>Discussione
 Nell'esempio è incluso un flusso di lavoro della finestra di progettazione e un flusso di lavoro codificato.

 Workflow Designer la versione della finestra di progettazione dell'esempio illustra come creare un flusso di lavoro nella finestra di progettazione. Sono inclusi i file seguenti:

- Program.cs: Include la `Main` funzione che esegue il flusso di lavoro di esempio.

- ReadString.cs: Attività personalizzata che legge un input dalla console.

- Sequence1. XAML: Flusso di lavoro creato utilizzando la finestra di progettazione che utilizza pick.

 Flusso di lavoro codificato la versione codificata dell'esempio illustra come creare un flusso di lavoro nella finestra di progettazione. Sono inclusi i file seguenti:

- Program.cs: Include la `Main` funzione che esegue il flusso di lavoro di esempio.

- ReadString.cs: Attività personalizzata che legge un input dalla console.

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Con Visual Studio 2010 aprire il file della soluzione pick. sln.

2. Per compilare la soluzione, premere CTRL+MAIUSC+B.

3. Per eseguire la soluzione, premere F5.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ed esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`
