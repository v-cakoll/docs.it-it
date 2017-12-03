---
title: Determinazione della durata di esecuzione del flusso di lavoro tramite traccia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c635dbd551eaba6ce338c38564480d0f5cfae553
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="determining-workflow-execution-duration-using-tracing"></a>Determinazione della durata di esecuzione del flusso di lavoro tramite traccia
In questo argomento viene illustrato come determinare il tempo necessario per l'esecuzione corretta di un flusso di lavoro indipendente tramite la traccia del flusso di lavoro.  
  
### <a name="to-determine-workflow-application-execution-duration-by-using-workflow-tracing"></a>Per determinare la durata di esecuzione di un'applicazione flusso di lavoro tramite la traccia del flusso di lavoro  
  
1.  Aprire [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  Selezionare **File**, **nuova**, **progetto**.  In **c#**, selezionare il **flusso di lavoro** nodo.  Selezionare **applicazione Console flusso di lavoro** dall'elenco dei modelli.  Denominare il nuovo progetto `WorkflowDurationTracing` e fare clic su **OK**.  
  
2.  Aprire Workflow1.xaml.  Trascinare un'attività <xref:System.Activities.Statements.Delay> nell'area di progettazione. Assegnare il valore 00.00.10 (dieci secondi) alla proprietà Duration dell'attività.  
  
3.  Aprire il Visualizzatore eventi fare clic su **avviare**, **eseguire**e l'immissione di `eventvwr.exe`.  
  
4.  Se è stata abilitata la traccia del flusso di lavoro, espandere **registri applicazioni e servizi**, **Microsoft**, **Windows**, **Server applicazioni-applicazioni** . Selezionare **vista**, **Mostra analitica e registri di Debug**. Fare doppio clic su **Debug** e selezionare **Attiva registro**. Lasciare aperto il Visualizzatore eventi in modo che sia possibile visualizzare le tracce dopo l'esecuzione del flusso di lavoro.  
  
5.  Premere CTRL+SHIFT+B per eseguire l'applicazione flusso di lavoro.  
  
6.  Nel Visualizzatore eventi trovare un recente evento con ID 1009 e un messaggio analogo al seguente. Annotare l'ora in cui il messaggio è stato registrato.  
  
 **Attività padre ', DisplayName: ', InstanceId: ' figlio pianificato l'attività 'WorkflowDurationTracking.Workflow1', DisplayName: 'Flussodilavoro1', InstanceId: '1'.**  
  
7.  Trovare un altro evento recente con ID 1001 e un messaggio analogo al seguente.  Sottrarre l'ora del messaggio precedente dal valore registrato per questo messaggio per determinare la durata di esecuzione del flusso di lavoro che deve essere di circa 10 secondi.  
  
 **WorkflowInstance con Id: '1bbac57b-3322-498e-9e27-8833fda3a5bf' completata nello stato Closed.**  
  
## <a name="see-also"></a>Vedere anche  
 [Analisi del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md)  
 [Monitoraggio dell'infrastruttura di App di Windows Server](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [Monitoraggio delle applicazioni con App Fabric](http://go.microsoft.com/fwlink/?LinkId=201275)
