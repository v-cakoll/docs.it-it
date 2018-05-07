---
title: TransactionScope di base
ms.date: 03/30/2017
ms.assetid: 1e22b76a-76de-43b4-9be7-7a86ed3d5a44
ms.openlocfilehash: fe6877c4b2d72dc3d571740395fd4dc92ca8e99c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="basic-transactionscope"></a>TransactionScope di base
Questo esempio è costituito da quattro scenari che vengono eseguiti illustrando come annidare istanze di <xref:System.Activities.Statements.TransactionScope>. Nel primo scenario viene illustrato l'annidamento di un'attività di terze parti di cui l'autore non dispone di informazioni sulla modalità di costruzione. Nel secondo e nel terzo scenario viene illustrato come vengono rispettati timeout, mentre nello scenario finale viene illustrata l'impostazione di <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A>.  
  
## <a name="nesting-of-transactionscopeactivity"></a>Annidamento di TransactionScopeActivity  
 Il flusso di lavoro per il primo scenario è costituito da una sequenza di due attività <xref:System.Activities.Statements.WriteLine> e una <xref:System.Activities.Statements.TransactionScope>. Il corpo di <xref:System.Activities.Statements.TransactionScope> è una sequenza delle altre due attività <xref:System.Activities.Statements.WriteLine>, un'attività personalizzata che stampa l'identificatore locale della transazione e un'attività di terze parti. L'attività di terze parti `TransactionScopeTest` contiene un oggetto <xref:System.Activities.Statements.TransactionScope> anche se l'autore del flusso di lavoro non ha modo di esserne a conoscenza. In questo scenario viene illustrato che le attività <xref:System.Activities.Statements.TransactionScope> possono essere annidate.  
  
## <a name="time-outs"></a>Timeout  
 Il flusso di lavoro per il secondo scenario è quasi identico al primo. `TransactionScopeTest` è stato sostituito con <xref:System.Activities.Statements.TransactionScope>. Il corpo di <xref:System.Activities.Statements.TransactionScope> ha un ritardo di cinque secondi e il timeout per la transazione è impostato su due secondi. Il valore del timeout per l'attività <xref:System.Activities.Statements.TransactionScope> esterna è impostato su 10 secondi. Notare che viene rispettato il timeout inferiore presente nell'ambito e la transazione scade.  
  
 Il flusso di lavoro per il terzo scenario è quasi identico al secondo scenario. L'attività di ritardo è stata spostata dal corpo dell'attività <xref:System.Activities.Statements.TransactionScope> interna immediatamente dopo di essa nella sequenza, ovvero il corpo dell'attività <xref:System.Activities.Statements.TransactionScope> esterna. La transazione scade ancora perché il timeout di due secondi dell'attività <xref:System.Activities.Statements.TransactionScope> interna non è più applicabile. La transazione scade a 10 secondi quando viene superato il timeout dell'attività <xref:System.Activities.Statements.TransactionScope> esterna.  
  
## <a name="aborting-on-transaction-failure"></a>Interruzione in caso di errore della transazione  
 Questo flusso di lavoro è simile al terzo scenario, salvo il fatto che i timeout sono stati sostituiti dalla proprietà <xref:System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure%2A>. Notare che i flag di tutti gli elementi figlio interni, se impostati, devono corrispondere all'attività <xref:System.Activities.Statements.TransactionScope> esterna. In questo scenario non corrispondono e quindi viene generata un'eccezione all'apertura del flusso di lavoro.  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  Aprire la soluzione BasicTransactionScopeSample.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Per compilare la soluzione, premere CTRL + MAIUSC + B o scegliere **Compila soluzione** dal **compilare** menu.  
  
3.  Una volta completata la compilazione, premere F5 o scegliere **Avvia debug** dal **Debug** menu. In alternativa è possibile premere CTRL + F5 o selezionare **Avvia senza eseguire debug** dal **Debug** menu per l'esecuzione senza debug.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\BasicTransactionScope`