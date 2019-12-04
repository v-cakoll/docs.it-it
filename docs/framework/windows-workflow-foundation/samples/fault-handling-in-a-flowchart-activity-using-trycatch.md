---
title: Gestione errori in un'attività Flowchart utilizzando TryCatch
ms.date: 03/30/2017
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
ms.openlocfilehash: 8e3ca59bc9743300a230877a6fbcbed5468a1589
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74710831"
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a>Gestione errori in un'attività Flowchart utilizzando TryCatch

In questo esempio viene illustrato come è possibile usare l'attività <xref:System.Activities.Statements.TryCatch> all'interno di un'attività del flusso di controllo complessa.

In questo esempio vengono passati un codice promozione e un numero di elementi figlio come variabili a un'attività <xref:System.Activities.Statements.Flowchart> che calcola un sconto in base a formule che corrispondono al codice di promozione. Nell'esempio è incluso codice imperativo e versioni della finestra di progettazione del flusso di lavoro dell'esempio.

Nella tabella seguente sono indicate in dettaglio le variabili dell'attività `CreateFlowchartWithFaults`.

|Parametri|Descrizione|
|----------------|-----------------|
|promoCode|Codice promozione. Tipo: String<br /><br /> I valori possibili con descrizione tra parentesi:<br /><br /> -Singolo (singolo)<br />-MNK (sposato senza figli).<br />-MWK (sposato con Kids.)|
|numKids|Numero di bambini. Tipo: int|

L'attività `CreateFlowchartWithFaults` usa un'attività <xref:System.Activities.Statements.FlowSwitch%601> che passa l'argomento `promoCode` e calcola lo sconto usando la formula seguente.

|Valore di `promoCode`|Sconto (%)|
|--------------------------|--------------------|
|Single|10|
|MNK|15|
|MWK|15 + (1-1/`numberOfKids`)\*10 **Nota:** potenzialmente, questo calcolo può generare un <xref:System.DivideByZeroException>. Viene quindi eseguito il wrapping del calcolo dello sconto in un'attività <xref:System.Activities.Statements.TryCatch> che rileva l'eccezione <xref:System.DivideByZeroException> e imposta lo sconto su zero.|

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Con Visual Studio 2010 aprire il file della soluzione FlowchartWithFaultHandling. sln.

2. Per compilare la soluzione, premere CTRL+MAIUSC+B.

3. Per eseguire la soluzione, premere F5.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`

## <a name="see-also"></a>Vedere anche

- [Flussi di lavoro del diagramma di flusso](../flowchart-workflows.md)
- [Eccezioni](../exceptions.md)
