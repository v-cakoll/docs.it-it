---
title: Modello di conferma automatica
ms.date: 03/30/2017
ms.assetid: 668aec65-78d3-4636-9c7b-deed643a18f9
ms.openlocfilehash: a032c05743b64fe58b0b187328b5216080ba6e19
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43552270"
---
# <a name="auto-confirm-pattern"></a>Modello di conferma automatica
Questa esempio è costituito da tre scenari in cui viene eseguita l'illustrazione di un'attività `AutoConfirmScope` personalizzata. Nel primo esempio viene illustrata l'esecuzione riuscita di una sequenza di quattro attività compensabili dove la seconda e la terza sono annidate in un oggetto `AutoConfirmScope`. Nel secondo esempio viene illustrata la stessa sequenza con un'eccezione che si verifica dopo l'esecuzione della quarta attività <xref:System.Activities.Statements.CompensableActivity>. Nel terzo scenario viene illustrata la stessa sequenza con un'eccezione che si verifica in `AutoConfirmScope` dopo il completamento del secondo <xref:System.Activities.Statements.CompensableActivity>.  
  
 Nell'esempio viene illustrato il modello di conferma automatica dove tutte le attività figlio compensabili vengono confermate al completamento riuscito dell'ambito. Questo modello definisce la durata di tutte le attività figlio compensabili, in quanto non possono più essere compensate o confermate.  
  
 L'ambito è costituito da un <xref:System.Activities.Statements.TryCatch> dove <xref:System.Activities.Statements.TryCatch.Try%2A> è un oggetto <xref:System.Activities.Statements.CompensableActivity> interno. Il corpo specificato dall'utente di `AutoConfirmScope` è il corpo dell'oggetto <xref:System.Activities.Statements.CompensableActivity> interno. Quando questo oggetto <xref:System.Activities.Statements.CompensableActivity> interno viene completato, produce <xref:System.Activities.Statements.CompensationToken> come argomento out. `AutoConfirmScope` usa <xref:System.Activities.Statements.TryCatch.Finally%2A> per controllare se è stato prodotto il token e in tal caso conferma l'attività <xref:System.Activities.Statements.CompensableActivity> interna. L'attività <xref:System.Activities.Statements.CompensableActivity> interna richiama la compensazione predefinita per qualsiasi attività compensabile eventualmente presente nel corpo.  
  
 Nel primo scenario viene illustrata l'esecuzione riuscita del flusso di lavoro e viene dimostrato che la seconda e terza attività compensabili sono già confermate quando il flusso di lavoro viene completato e la prima e la quarta vengono confermate. In questo modo viene prodotto un ordine di conferma tre, due, quattro e uno.  
  
 Nel secondo scenario viene illustrata un'eccezione dopo il completamento delle quattro attività compensabili. Poiché le attività compensabili due e tre sono già confermate, non sono interessate, ma le attività uno e quattro vengono compensate. In questo modo viene prodotto l'ordine conferma tre, conferma due, compensa quattro e compensa uno.  
  
 Nello scenario finale viene illustrata l'esecuzione non riuscita di `AutoConfirmScope`. In questo scenario si verifica un'eccezione dopo il completamento della seconda <xref:System.Activities.Statements.CompensableActivity>. Poiché le attività compensabili terza e quarta non sono state eseguite, non sono interessate. Poiché l'ambito non è stato completato correttamente, la seconda <xref:System.Activities.Statements.CompensableActivity> non viene confermata. In questo modo viene prodotto un ordine di compensazione di due quindi uno.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione AutoConfirmSample.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere CTRL+F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Compensation\AutoConfirm`