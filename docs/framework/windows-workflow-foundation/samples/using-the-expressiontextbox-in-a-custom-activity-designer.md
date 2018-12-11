---
title: Utilizzo di ExpressionTextBox in un ActivityDesigner personalizzato
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: ee9da26625d772eda6100fc4d0db0469941bdb0d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149939"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a>Utilizzo di ExpressionTextBox in un ActivityDesigner personalizzato
In questo esempio viene illustrato come usare l'oggetto <xref:System.Activities.Presentation.View.ExpressionTextBox> in un ActivityDesigner personalizzato. L'attività personalizzata, `MultiAssign`, assegna due valori stringa a due variabili di stringa. Alcuni controlli <xref:System.Activities.Presentation.View.ExpressionTextBox> vengono associati a oggetti <xref:System.Activities.InArgument> mentre altri a oggetti <xref:System.Activities.OutArgument>.

## <a name="sample-details"></a>Dettagli dell'esempio
 L'oggetto `ArgumentToExpressionConverter` è il convertitore di tipi usato in caso di associazione di espressioni agli argomenti. La proprietà `ConverterParameter` deve essere impostata su `In`, `Out`, a seconda delle esigenze. `InOut` non è supportato.

 Il `UseLocationExpression` attributo è usato in `OutArgument`per specificare che l'espressione deve essere un'espressione L-value ("valore a sinistra" o "valore location"). Nella maggior parte dei casi, un'espressione L-value è un identificatore di Visual Basic valido usato per indicare che l'oggetto `OutArgument` restituito è una variabile o un nome dell'argomento.

 L'attributo `MaxLines` viene impostato su uno in questo esempio mentre `MinLines` non viene impostato. Pertanto, l'oggetto <xref:System.Activities.Presentation.View.ExpressionTextBox> è una dimensione fissa di una riga, indipendentemente dalla quantità di testo digitato dall'utente. Per consentire all'oggetto <xref:System.Activities.Presentation.View.ExpressionTextBox> di ingrandirsi per adattarsi all'input dell'utente, impostare per `MaxLines` un valore maggiore rispetto a `MinLines`.

 Un oggetto ExpressionTextBox può essere associato solo agli argomenti e non alle proprietà CLR.

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1.  Con Visual Studio 2010, aprire il file Expressiontextboxsample.

2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.

#### <a name="to-run-this-sample"></a>Per eseguire l'esempio

1.  Aggiungere una nuova applicazione console flusso di lavoro alla soluzione.

2.  Aggiungere un riferimento per la **ExpressionTextBoxSample** progetto dal nuovo progetto applicazione Console flusso di lavoro.

3.  Compilare la soluzione.

4.  Trascinare il **MultiAssign** attività dalla casella degli strumenti e rilasciarla nel flusso di lavoro.

> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>  
 [Sviluppo di applicazioni con Progettazione flussi di lavoro](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
