---
title: Attività NoPersistScope
ms.date: 03/30/2017
ms.assetid: 9a0baeb7-a05c-4fac-b905-252758cb71bb
ms.openlocfilehash: 6543756594b6734aec39bf22c5ab6215605341b1
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45529251"
---
# <a name="nopersistscope-activity"></a>Attività NoPersistScope
In questo esempio viene illustrato come modificare uno stato Non-serializable e Disposable all'interno di un flusso di lavoro. È importante che i flussi di lavoro non tentino di rendere persistente lo stato Non-serializable e che venga eseguita la pulizia degli oggetti eliminabili dopo essere stati usati nel flusso di lavoro.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Attività personalizzata `NoPersistScope` e finestra di progettazione.  
  
## <a name="using-the-nopersistzone-activity"></a>Utilizzo dell'attività NoPersistZone  
 Quando viene eseguito il flusso di lavoro di esempio, un'attività personalizzata denominata `CreateTextWriter` crea un oggetto di tipo <xref:System.IO.TextWriter> e lo salva in una variabile del flusso di lavoro. <xref:System.IO.TextWriter> è un oggetto <xref:System.IDisposable>. Questo oggetto <xref:System.IO.TextWriter>, configurato per scrivere in un file denominato 'out.txt' nella directory in cui viene eseguito l'esempio, viene usato da un'attività <xref:System.Activities.Statements.WriteLine> poiché restituisce qualsiasi testo digitato nella console.  
  
 La logica echo viene eseguita all'interno di un'attività `NoPersistScope` (il cui codice fa anche parte di questo esempio) che evita la persistenza del flusso di lavoro. Se si digita `unload` nella console, l'host tenta di rendere persistente l'istanza del flusso di lavoro, ma questa operazione scade poiché il flusso di lavoro rimane all'interno di un `NoPersistScope`. Il flusso di lavoro usa anche un'attività personalizzata denominata `Dispose` per eliminare l'oggetto <xref:System.IO.TextWriter> quando il flusso di lavoro viene completato utilizzandolo. L'attività `Dispose` viene posizionata all'interno del blocco <xref:System.Activities.Statements.TryCatch.Finally%2A> dell'attività <xref:System.Activities.Statements.TryCatch> in cui viene dichiarata la variabile <xref:System.IO.TextWriter>, per assicurarsi che venga eseguita anche se si dovesse verificare un'eccezione durante l'esecuzione del blocco Try.  
  
 È possibile digitare `exit` per completare l'istanza del flusso di lavoro e uscire dal programma.  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  Aprire la soluzione NoPersistZone.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Per compilare la soluzione, premere CTRL + MAIUSC + B o scegliere **Compila soluzione** dalle **compilazione** menu.  
  
3.  Una volta completata la compilazione, premere F5 o selezionare **Avvia debug** dal **Debug** dal menu in alternativa, è possibile premere CTRL+F5 o selezionare **Avvia senza eseguire debug** dal **Debug** menu per l'esecuzione senza debug.  
  
#### <a name="to-cleanup-optional"></a>Per eseguire la pulizia (facoltativo)  
  
1.  Per rimuovere l'archivio di istanze SQL, eseguire Cleanup.cmd.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NoPersistScope`