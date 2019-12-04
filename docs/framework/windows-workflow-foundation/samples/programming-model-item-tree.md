---
title: Programmazione dell'albero degli elementi del modello
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: efda69ac568b0ad9c5fdcf4d42722c5b7dadd3f3
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715671"
---
# <a name="programming-model-item-tree"></a>Programmazione dell'albero degli elementi del modello
In questo esempio viene illustrato come spostarsi nell'albero <xref:System.Activities.Presentation.Model.ModelItem> utilizzando data binding dichiarativo dalla visualizzazione albero Windows Presentation Foundation (WPF).

## <a name="sample-details"></a>Dettagli dell'esempio
 L'albero <xref:System.Activities.Presentation.Model.ModelItem> è l'astrazione usata dall'infrastruttura di Windows Progettazione flussi di lavoro per esporre i dati sull'istanza sottostante in fase di modifica. La figura seguente illustra i diversi livelli di infrastruttura all'interno del Progettazione flussi di lavoro.

 ![Diagramma che illustra l'architettura del Progettazione flussi di lavoro.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 Un oggetto <xref:System.Activities.Presentation.Model.ModelItem> è costituito da un puntatore al valore sottostante e da una raccolta di oggetti <xref:System.Activities.Presentation.Model.ModelProperty>. Un oggetto <xref:System.Activities.Presentation.Model.ModelProperty> è costituito, a sua volta, da dati quali il nome e il tipo della proprietà e quindi da un puntatore al valore che, a sua volta, è un altro <xref:System.Activities.Presentation.Model.ModelItem>. Un convertitore di valori viene usato per modificare alcuni oggetti <xref:System.Activities.Presentation.Model.ModelItem>restituiti da <xref:System.Activities.Presentation.Model.ModelProperty> in modo che siano riportati correttamente nella visualizzazione albero. Nell'esempio viene dimostrato quindi come programmare in modo imperativo rispetto all'albero <xref:System.Activities.Presentation.Model.ModelItem> usando la sintassi imperativa, come nell'esempio seguente.

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Aprire la soluzione ProgrammingModelItemTree. sln in Visual Studio 2010.

2. Compilare la soluzione scegliendo **Compila soluzione** dal menu **Compila** .

3. Premere F5 per eseguire l'applicazione. Il form WPF viene quindi visualizzato.

4. Fare clic sul pulsante **Load WF** per caricare il <xref:System.Activities.Presentation.Model.ModelItem> e associarlo alla visualizzazione albero.

5. Facendo clic sul pulsante **modifica albero degli elementi del modello** viene eseguito il codice precedente per aggiungere un elemento nell'albero e impostare una proprietà.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.IValueConverter>
