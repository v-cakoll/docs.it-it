---
title: Uso di delegati di attività
ms.date: 03/30/2017
ms.assetid: e33cf876-8979-440b-9b23-4a12d1139960
ms.openlocfilehash: cbcc8f8e498be4f79f8fed5af7cd3557d7c55981
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837571"
---
# <a name="using-activity-delegates"></a>Uso di delegati di attività
I delegati di attività consentono agli autori di attività di esporre callback con firme specifiche, per cui gli utenti dell'attività possono fornire gestori in base all'attività. Sono disponibili due tipi di delegati di attività: <xref:System.Activities.ActivityAction%601>, usato per definire i delegati di attività senza un valore restituito, e <xref:System.Activities.ActivityFunc%601>, usato per definire i delegati di attività con un valore restituito.

I delegati di attività sono utili in scenari in cui un'attività figlio deve disporre di una determinata firma. Ad esempio, un'attività <xref:System.Activities.Statements.While> può contenere qualsiasi tipo di attività figlio senza vincoli, ma il corpo di un'attività <xref:System.Activities.Statements.ForEach%601> è un oggetto <xref:System.Activities.ActivityAction%601> e l'attività figlio che viene eseguita alla fine dall'oggetto <xref:System.Activities.Statements.ForEach%601> deve disporre di un oggetto <xref:System.Activities.InArgument%601> dello stesso tipo dei membri della raccolta enumerata dall'oggetto <xref:System.Activities.Statements.ForEach%601>.

## <a name="using-activityaction"></a>Uso di ActivityAction

Diverse attività [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] usano le azioni di attività, ad esempio le attività <xref:System.Activities.Statements.Catch> e <xref:System.Activities.Statements.ForEach%601>. In ogni caso, l'azione di attività rappresenta un percorso in cui l'autore del flusso di lavoro specifica un'attività per fornire il comportamento desiderato quando si crea un flusso di lavoro usando una di queste attività. Nell'esempio seguente, si usa un'attività <xref:System.Activities.Statements.ForEach%601> per visualizzare il testo nella finestra della console. Il corpo dell'oggetto <xref:System.Activities.Statements.ForEach%601> viene specificato tramite un oggetto <xref:System.Activities.ActivityAction%601> che corrisponde al tipo dell'oggetto <xref:System.Activities.Statements.ForEach%601> che è una stringa. L'argomento <xref:System.Activities.Statements.WriteLine> dell'attività <xref:System.Activities.ActivityDelegate.Handler%2A> specificata nell'oggetto <xref:System.Activities.Statements.WriteLine.Text%2A> è associato ai valori stringa della raccolta scorsa dall'attività <xref:System.Activities.Statements.ForEach%601>.

[!code-csharp[CFX_ActivityExample#6](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#6)]

L'oggetto ActionArgument è usato per propagare i singoli elementi della raccolta in WriteLine. Quando il flusso di lavoro viene richiamato, l'output seguente viene visualizzato nella console.

```console
HelloWorld.
```

Negli esempi di questo argomento viene usata la sintassi di inizializzazione oggetti che può essere utile per creare definizioni del flusso di lavoro in codice in quanto fornisce una visualizzazione gerarchica delle attività nel flusso di lavoro e consente di illustrare la relazione tra le attività. Non è previsto alcun requisito per usare la sintassi di inizializzazione oggetti quando si creano flussi di lavoro a livello di codice. L'esempio seguente rappresenta l'equivalente funzionale dell'esempio precedente.

[!code-csharp[CFX_ActivityExample#7](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#7)]

Per ulteriori informazioni sugli inizializzatori di oggetto, vedere [procedura: inizializzare oggetti senza chiamare un costruttoreC# (Guida per programmatori)](../../csharp/programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md) e [procedura: dichiarare un oggetto utilizzando un inizializzatore di oggetto (Visual Basic)](../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md).

Nell'esempio seguente, un'attività <xref:System.Activities.Statements.TryCatch> è usata in un flusso di lavoro. Un'eccezione <xref:System.ApplicationException> viene generata dal flusso di lavoro e gestita da un'attività <xref:System.Activities.Statements.Catch%601>. Il gestore per l'azione dell'attività dell'attività <xref:System.Activities.Statements.Catch%601> è un'attività <xref:System.Activities.Statements.WriteLine> e il dettaglio dell'eccezione viene propagato tramite il <xref:System.Activities.DelegateInArgument%601>di `ex`.

[!code-csharp[CFX_WorkflowApplicationExample#33](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#33)]

Quando si crea un'attività personalizzata che definisce un oggetto <xref:System.Activities.ActivityAction%601>, usare un oggetto <xref:System.Activities.Statements.InvokeAction%601> per modellare la chiamata di tale oggetto <xref:System.Activities.ActivityAction%601>. In questo esempio viene definita un'attività `WriteLineWithNotification` personalizzata. Questa attività è costituita da un oggetto <xref:System.Activities.Statements.Sequence> che contiene un'attività <xref:System.Activities.Statements.WriteLine> seguita da un oggetto <xref:System.Activities.Statements.InvokeAction%601> che richiama un oggetto <xref:System.Activities.ActivityAction%601> che accetta un argomento di tipo stringa.

[!code-csharp[CFX_ActivityExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#1)]

Quando un flusso di lavoro viene creato usando l'attività `WriteLineWithNotification`, l'autore del flusso di lavoro specifica la logica personalizzata desiderata nella proprietà <xref:System.Activities.ActivityDelegate.Handler%2A> dell'azione dell'attività. In questo esempio viene creato un flusso di lavoro che usa l'attività `WriteLineWithNotification` e un'attività <xref:System.Activities.Statements.WriteLine> viene usata come proprietà <xref:System.Activities.ActivityDelegate.Handler%2A>.

[!code-csharp[CFX_ActivityExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#2)]

Sono disponibili più versioni generiche degli oggetti <xref:System.Activities.Statements.InvokeAction%601> e <xref:System.Activities.ActivityAction%601> forniti per passare uno o più argomenti.

## <a name="using-activityfunc"></a>Uso di ActivityFunc

L'oggetto <xref:System.Activities.ActivityAction%601> è utile quando l'attività non restituisce alcun valore di risultato, mentre l'oggetto <xref:System.Activities.ActivityFunc%601> è usato quando viene restituito un valore di risultato. Quando si crea un'attività personalizzata che definisce un oggetto <xref:System.Activities.ActivityFunc%601>, usare un oggetto <xref:System.Activities.Expressions.InvokeFunc%601> per modellare la chiamata di tale oggetto <xref:System.Activities.ActivityFunc%601>. Nell'esempio seguente viene definita un'attività `WriteFillerText` . Per fornire il testo di riempimento, viene specificato un oggetto <xref:System.Activities.Expressions.InvokeFunc%601> che accetta un argomento Integer e dispone di un risultato di stringa. Una volta recuperato il testo di riempimento, viene visualizzato nella console tramite un'attività <xref:System.Activities.Statements.WriteLine>.

[!code-csharp[CFX_ActivityExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#3)]

Per fornire il testo, è necessario usare un'attività che accetta un argomento `int` e dispone di un risultato di stringa. In questo esempio viene mostrata un'attività `TextGenerator` che soddisfa questi requisiti.

[!code-csharp[CFX_ActivityExample#4](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#4)]

Per usare l'attività `TextGenerator` con l'attività `WriteFillerText`, specificarla come proprietà <xref:System.Activities.ActivityDelegate.Handler%2A>.

[!code-csharp[CFX_ActivityExample#5](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#5)]
