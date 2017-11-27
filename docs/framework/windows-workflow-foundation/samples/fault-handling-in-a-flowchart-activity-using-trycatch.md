---
title: "Gestione errori in un'attività Flowchart utilizzando TryCatch"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 490647f8ea3662f046cadecf5a97761c43b357f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a>Gestione errori in un'attività Flowchart utilizzando TryCatch
In questo esempio viene illustrato come è possibile usare l'attività <xref:System.Activities.Statements.TryCatch> all'interno di un'attività del flusso di controllo complessa.  
  
 In questo esempio vengono passati un codice promozione e un numero di elementi figlio come variabili a un'attività <xref:System.Activities.Statements.Flowchart> che calcola un sconto in base a formule che corrispondono al codice di promozione. Nell'esempio è incluso codice imperativo e versioni della finestra di progettazione del flusso di lavoro dell'esempio.  
  
 Nella tabella seguente sono indicate in dettaglio le variabili dell'attività `CreateFlowchartWithFaults`.  
  
|Parametri|Descrizione|  
|----------------|-----------------|  
|promoCode|Codice promozione. Tipo: String<br /><br /> I valori possibili con descrizione tra parentesi:<br /><br /> -Singolo (Single)<br />-MNK (sposato / a senza bambini.)<br />-Mwk (sposato / con bambini.)|  
|numKids|Numero di bambini. Tipo: int|  
  
 L'attività `CreateFlowchartWithFaults` usa un'attività <xref:System.Activities.Statements.FlowSwitch%601> che passa l'argomento `promoCode` e calcola lo sconto usando la formula seguente.  
  
|Valore di `promoCode`|Sconto (%)|  
|--------------------------|--------------------|  
|Single|10|  
|MNK|15|  
|MWK|15 + (1-1 /`numberOfKids`)\*10 **Nota:** potenzialmente, questo calcolo può generare un <xref:System.DivideByZeroException>. Viene quindi eseguito il wrapping del calcolo dello sconto in un'attività <xref:System.Activities.Statements.TryCatch> che rileva l'eccezione <xref:System.DivideByZeroException> e imposta lo sconto su zero.|  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione FlowchartWithFaultHandling.sln.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Per eseguire la soluzione, premere F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## <a name="see-also"></a>Vedere anche  
 [Flussi di lavoro del diagramma di flusso](../../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)  
 [Eccezioni](../../../../docs/framework/windows-workflow-foundation/exceptions.md)
