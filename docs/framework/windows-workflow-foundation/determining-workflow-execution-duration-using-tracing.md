---
title: Determinazione della durata di esecuzione del flusso di lavoro tramite traccia
ms.date: 03/30/2017
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
ms.openlocfilehash: c51fdf4543939fc068092b84e02eeb5f52e77d6d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486281"
---
# <a name="determining-workflow-execution-duration-using-tracing"></a>Determinazione della durata di esecuzione del flusso di lavoro tramite traccia
In questo argomento viene illustrato come determinare il tempo necessario per l'esecuzione corretta di un flusso di lavoro indipendente tramite la traccia del flusso di lavoro.  
  
### <a name="to-determine-workflow-application-execution-duration-by-using-workflow-tracing"></a>Per determinare la durata di esecuzione di un'applicazione flusso di lavoro tramite la traccia del flusso di lavoro  
  
1.  Aprire [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  Selezionare **File**, **nuove**, **progetto**.  Sotto **c#**, selezionare la **flusso di lavoro** nodo.  Selezionare **applicazione Console flusso di lavoro** dall'elenco dei modelli.  Denominare il nuovo progetto `WorkflowDurationTracing` e fare clic su **OK**.  
  
2.  Aprire Workflow1.xaml.  Trascinare un'attività <xref:System.Activities.Statements.Delay> nell'area di progettazione. Assegnare il valore 00.00.10 (dieci secondi) alla proprietà Duration dell'attività.  
  
3.  Aprire il Visualizzatore eventi facendo **avviare**, **eseguito**e l'immissione di `eventvwr.exe`.  
  
4.  Se non è stata abilitata la traccia del flusso di lavoro, espandere **registri applicazioni e servizi**, **Microsoft**, **Windows**, **Server applicazioni-applicazioni** . Selezionare **View**, **mostrano analitici e i registri Debug**. Fare doppio clic su **Debug** e selezionare **Attiva registro**. Lasciare aperto il Visualizzatore eventi in modo che sia possibile visualizzare le tracce dopo l'esecuzione del flusso di lavoro.  
  
5.  Premere CTRL+SHIFT+B per eseguire l'applicazione flusso di lavoro.  
  
6.  Nel Visualizzatore eventi trovare un recente evento con ID 1009 e un messaggio analogo al seguente. Annotare l'ora in cui il messaggio è stato registrato.  
  
 **Attività padre ', DisplayName: ', InstanceId: ' figlio pianificato l'attività 'Rilevamentodurataflussodilavoro.flussodilavoro1', DisplayName: 'Flussodilavoro1', InstanceId: '1'.**  
  
7.  Trovare un altro evento recente con ID 1001 e un messaggio analogo al seguente.  Sottrarre l'ora del messaggio precedente dal valore registrato per questo messaggio per determinare la durata di esecuzione del flusso di lavoro che deve essere di circa 10 secondi.  
  
 **WorkflowInstance con Id: '1bbac57b-3322-498e-9e27-8833fda3a5bf' è stata completata nello stato Closed.**  
  
## <a name="see-also"></a>Vedere anche  
 [Analisi del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md)  
 [Monitoraggio dell'infrastruttura di App di Windows Server](https://go.microsoft.com/fwlink/?LinkId=201273)  
 [Monitoraggio delle applicazioni con App Fabric](https://go.microsoft.com/fwlink/?LinkId=201275)
