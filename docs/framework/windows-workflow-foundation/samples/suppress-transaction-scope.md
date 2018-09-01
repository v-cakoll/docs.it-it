---
title: Eliminare l'ambito della transazione
ms.date: 03/30/2017
ms.assetid: 49fb6dd4-30d4-4067-925c-c5de44c8c740
ms.openlocfilehash: 44814d66a4de4b3e72bb33eb46019eb1088ab040
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385194"
---
# <a name="suppress-transaction-scope"></a>Eliminare l'ambito della transazione
In questo esempio viene illustrato come modificare un'attività `SuppressTransactionScope` personalizzata per annullare la transazione di runtime di ambiente, se presente.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 L'attività personalizzata è utile per impedire che una transazione venga propagata a un altro servizio se il flusso della transazione risulta indesiderabile per un particolare scenario. Nell'esecuzione del flusso di lavoro è presente il supporto incorporato per eliminare la transazione di ambiente nella classe <xref:System.Activities.NativeActivity>, ma per usare questo supporto è necessario modificare un oggetto <xref:System.Activities.NativeActivity> personalizzato come quello usato in questo esempio.  
  
 Lo scenario è costituito da tre parti. Innanzitutto, un oggetto <xref:System.Activities.Statements.TransactionScope> crea una transazione di runtime che diventa di ambiente. Questa operazione viene verificata da un'attività personalizzata che stampa gli identificatori locali e distribuiti della transazione. La transazione viene quindi propagata a un servizio remoto prima di iniziare la seconda parte. Durante la seconda parte, il flusso di lavoro apre un'attività `SuppressTransactionScope` e ripete di nuovo il processo di stampa degli identificatori della transazione e di propagazione della transazione. L'attività personalizzata non trova tuttavia una transazione di ambiente e il messaggio propagato al servizio non contiene la transazione. Di conseguenza, il servizio crea una transazione e ciò significa che l'ID distribuito stampato sul client e il servizio non corrispondono. La parte finale si verifica dopo la chiusura di `SuppressTransactionScope` e la transazione di runtime diventa nuovamente di ambiente, come risulta da un altro messaggio al servizio con un identificatore distribuito che corrisponde all'identificatore del primo messaggio.  
  
 L'attività stessa deriva da <xref:System.Activities.NativeActivity> perché deve pianificare un'attività figlio e aggiungere una proprietà di esecuzione. `SuppressTransactionScope` dispone di un oggetto <xref:System.Activities.Variable> di tipo <xref:System.Activities.RuntimeTransactionHandle> che deve essere usato al posto di un campo di istanza di tipo <xref:System.Activities.RuntimeTransactionHandle> perché è necessario inizializzare l'handle. `Variable<RuntimeTransactionHandle>` viene aggiunto ai metadati dell'attività come una variabile di implementazione in quanto è usato solo internamente.  
  
 Durante l'esecuzione dell'attività, viene controllato innanzitutto se è stato specificato un corpo e, in tal caso, la proprietà `SuppressTransaction` viene impostata su <xref:System.Activities.RuntimeTransactionHandle>. Una volta impostata, la proprietà viene aggiunta alle proprietà di esecuzione e diventa di ambiente. Ciò significa che qualsiasi attività figlio di `SuppressTransactionScope` è in grado di visualizzare la proprietà, pertanto viene applicata l'eliminazione della transazione di runtime e viene generata un'eccezione da parte di un oggetto <xref:System.Activities.Statements.TransactionScope> annidato. Una volta aggiunto l'handle alle proprietà di esecuzione, viene pianificata l'esecuzione del corpo.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire la soluzione SuppressTransactionScope.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Per compilare la soluzione, premere CTRL + MAIUSC + B o scegliere **Compila soluzione** dalle **compilazione** menu.  
  
3.  Una volta completata la compilazione, la soluzione e scegliere **Imposta progetti di avvio**. Nella finestra di dialogo, selezionare **progetti di avvio multipli** e assicurarsi che l'azione per entrambi i progetti sia **avviare**.  
  
4.  Premere F5 o selezionare **Avvia debug** dalle **Debug** menu. In alternativa, è possibile premere CTRL+F5 o selezionare **Avvia senza eseguire debug** dalle **Debug** menu per l'esecuzione senza debug.  
  
    > [!NOTE]
    >  Il server deve essere in esecuzione prima dell'avvio del client. L'output dalla finestra della console che ospita il servizio indica quando è stato avviato.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\SuppressTransactionScope`