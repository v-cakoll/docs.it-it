---
title: Programmazione dell'albero degli elementi del modello
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: f14b140fdac95f3763cc5625841a725793876fa4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142693"
---
# <a name="programming-model-item-tree"></a>Programmazione dell'albero degli elementi del modello
In questo esempio viene <xref:System.Activities.Presentation.Model.ModelItem> illustrato come spostarsi nella struttura ad albero utilizzando l'associazione dati dichiarativa dalla visualizzazione albero di Windows Presentation Foundation (WPF).

## <a name="sample-details"></a>Dettagli dell'esempio
 La <xref:System.Activities.Presentation.Model.ModelItem> struttura ad albero è l'astrazione utilizzata dall'infrastruttura di Progettazione flussi di lavoro di Windows per esporre i dati relativi all'istanza sottostante in corso di modifica. Nella figura seguente viene illustrata una rappresentazione dei vari livelli dell'infrastruttura all'interno di Progettazione flussi di lavoro.

 ![Diagramma che mostra l'architettura di Progettazione flussi di lavoro.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 Un oggetto <xref:System.Activities.Presentation.Model.ModelItem> è costituito da un puntatore al valore sottostante e da una raccolta di oggetti <xref:System.Activities.Presentation.Model.ModelProperty>. Un oggetto <xref:System.Activities.Presentation.Model.ModelProperty> è costituito, a sua volta, da dati quali il nome e il tipo della proprietà e quindi da un puntatore al valore che, a sua volta, è un altro <xref:System.Activities.Presentation.Model.ModelItem>. Un convertitore di valori viene usato per modificare alcuni oggetti <xref:System.Activities.Presentation.Model.ModelItem>restituiti da <xref:System.Activities.Presentation.Model.ModelProperty> in modo che siano riportati correttamente nella visualizzazione albero. Nell'esempio viene dimostrato quindi come programmare in modo imperativo rispetto all'albero <xref:System.Activities.Presentation.Model.ModelItem> usando la sintassi imperativa, come nell'esempio seguente.

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a>Per usare questo esempio

1. Aprire la soluzione ProgrammingModelItemTree.sln in Visual Studio 2010.Open the ProgrammingModelItemTree.sln solution in Visual Studio 2010.

2. Compilare la soluzione selezionando **Compila soluzione** dal menu **Compila** .Build -

3. Premere F5 per eseguire l'applicazione. Viene quindi visualizzato il form WPF.

4. Fare clic sul pulsante <xref:System.Activities.Presentation.Model.ModelItem> Carica **WF** per caricare e associarlo alla vista ad albero.

5. Facendo clic sul pulsante **Modifica struttura ad albero degli elementi** del modello viene eseguito il codice precedente per aggiungere un elemento nella struttura ad albero e impostare una proprietà.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.IValueConverter>
