---
title: Ambito di istruzioni della transazione
ms.date: 03/30/2017
ms.assetid: 37141708-a29f-4b6a-81fe-f8a11f825061
ms.openlocfilehash: fa1da6df5ad5256665610c9b3c2df7d706cef63c
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43871251"
---
# <a name="transaction-convoy-scope"></a>Ambito di istruzioni della transazione
In questo esempio viene illustrato come creare un modello di attività di messaggistica di una serie di istruzioni parallele insieme a un oggetto <xref:System.ServiceModel.Activities.TransactedReceiveScope> per modellare un protocollo in cui possono verificarsi diverse operazioni in qualsiasi ordine, tutte nella stessa transazione. In questo esempio viene inoltre illustrato in che modo <xref:System.ServiceModel.Activities.TransactedReceiveScope> crea automaticamente una nuova transazione quando non ne viene propagata una al server, in modo che il client non utilizzi alcuna transazione.  
  
 L'esempio è costituito da due progetti di flusso di lavoro che rappresentano client e server. Il progetto client esegue un flusso di lavoro che inizia con l'invio di un messaggio per il bootstrap del flusso di lavoro del server che inizializza una correlazione e avvia un ambito transazionale per il resto delle attività di messaggistica. L'attività <xref:System.Activities.Statements.Sequence> del client contiene una coppia <xref:System.ServiceModel.Activities.Send> e <xref:System.ServiceModel.Activities.ReceiveReply>iniziale e quindi un'attività <xref:System.Activities.Statements.Parallel> con tre rami. Ogni ramo invia un messaggio unidirezionale al server. La proprietà <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> dell'attività <xref:System.Activities.Statements.Parallel> viene impostata su `false` in modo che tutti e tre i rami siano completati.  
  
 Il flusso di lavoro server è simile al flusso di lavoro client con l'eccezione che le attività di messaggistica sono orientate verso il lato server della comunicazione e sono contenuti all'interno di un'attività <xref:System.ServiceModel.Activities.TransactedReceiveScope>, in modo che ogni lavoro venga eseguito nella stessa transazione. Quando il primo messaggio viene ricevuto nel server, viene creata una transazione che diventa di ambiente per l'ambito del corpo di <xref:System.ServiceModel.Activities.TransactedReceiveScope>, in modo che qualsiasi attività all'interno di questo ambito possa accedere alla transazione. Successivamente tutte le ricezioni vengono eseguite in parallelo. È necessario che tutte le ricezioni vengano eseguite esattamente una volta come descritto dalla condizione di completamento nell'attività parallela. Alla fine del corpo <xref:System.ServiceModel.Activities.TransactedReceiveScope> è presente un punto di persistenza implicito e anche l'operazione di persistenza viene eseguita nella stessa transazione.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione ParallelConvoySample.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Assicurarsi che entrambi i progetti siano impostati per l'avvio.  
  
    1.  Nelle **Esplora soluzioni**, la soluzione e scegliere **Imposta progetti di avvio**.  
  
    2.  Selezionare **progetti di avvio multipli** e verificare che l'azione per entrambi i progetti è impostata su **avviare**.  
  
4.  Per eseguire la soluzione, premere CTRL+F5.  
  
     Il server stampa `Server is running` per indicare che è pronto.  
  
     Premere un tasto qualsiasi nella finestra della console del client per avviare l'esempio.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedConvoyScope`