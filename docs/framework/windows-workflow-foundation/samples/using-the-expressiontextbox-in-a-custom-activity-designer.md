---
title: Utilizzo di ExpressionTextBox in un ActivityDesigner personalizzato
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: 6d3df9e18c7239f0e4695509d80edfd02e9a9d6f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182764"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a>Utilizzo di ExpressionTextBox in un ActivityDesigner personalizzato
In questo esempio viene illustrato come usare l'oggetto <xref:System.Activities.Presentation.View.ExpressionTextBox> in un ActivityDesigner personalizzato. L'attività personalizzata, `MultiAssign`, assegna due valori stringa a due variabili di stringa. Alcuni controlli <xref:System.Activities.Presentation.View.ExpressionTextBox> vengono associati a oggetti <xref:System.Activities.InArgument> mentre altri a oggetti <xref:System.Activities.OutArgument>.

## <a name="sample-details"></a>Dettagli dell'esempio
 L'oggetto `ArgumentToExpressionConverter` è il convertitore di tipi usato in caso di associazione di espressioni agli argomenti. La proprietà `ConverterParameter` deve essere impostata su `In`, `Out`, a seconda delle esigenze. `InOut` non è supportata.

 L'attributo `UseLocationExpression` `OutArgument`viene utilizzato in s per specificare che l'espressione deve essere un'espressione di valore L ("valore sinistro" o "valore di posizione"). Nella maggior parte dei casi, un'espressione L-value è un identificatore di Visual Basic valido usato per indicare che l'oggetto `OutArgument` restituito è una variabile o un nome dell'argomento.

 L'attributo `MaxLines` viene impostato su uno in questo esempio mentre `MinLines` non viene impostato. Pertanto, l'oggetto <xref:System.Activities.Presentation.View.ExpressionTextBox> è una dimensione fissa di una riga, indipendentemente dalla quantità di testo digitato dall'utente. Per consentire all'oggetto <xref:System.Activities.Presentation.View.ExpressionTextBox> di ingrandirsi per adattarsi all'input dell'utente, impostare per `MaxLines` un valore maggiore rispetto a `MinLines`.

 Un oggetto ExpressionTextBox può essere associato solo agli argomenti e non alle proprietà CLR.

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Utilizzando Visual Studio 2010, aprire il file ExpressionTextBoxSample.sln.

2. Per compilare la soluzione, premere CTRL+MAIUSC+B.

#### <a name="to-run-this-sample"></a>Per eseguire questo esempio

1. Aggiungere una nuova applicazione console flusso di lavoro alla soluzione.

2. Aggiungere un riferimento al progetto **ExpressionTextBoxSample** dal nuovo progetto Applicazione console flusso di lavoro.

3. Compilare la soluzione.

4. Trascinare l'attività **MultiAssign** dalla casella degli strumenti e rilasciarla nel flusso di lavoro.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.Presentation.View.ExpressionTextBox>
- [Sviluppo di applicazioni con Progettazione flussi di lavoro](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
