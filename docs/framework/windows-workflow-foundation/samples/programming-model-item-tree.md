---
title: Programmazione dell'albero degli elementi del modello
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 497aa75214bdbbefa7f09ef56fe96926c2461ed6
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="programming-model-item-tree"></a>Programmazione dell'albero degli elementi del modello
In questo esempio viene illustrato come passare il <xref:System.Activities.Presentation.Model.ModelItem> albero usando l'associazione dati dichiarativa dalla visualizzazione albero Windows Presentation Foundation (WPF).  
  
## <a name="sample-details"></a>Dettagli dell'esempio  
 La struttura ad albero <xref:System.Activities.Presentation.Model.ModelItem> è l'astrazione usata dall'infrastruttura [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] per esporre i dati sull'istanza sottostante in fase di modifica. Nell'illustrazione seguente viene fornita una descrizione dei vari livelli dell'infrastruttura all'interno di [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].  
  
 ![Architettura della finestra di progettazione del flusso di lavoro](../../../../docs/framework/windows-workflow-foundation/samples/media/workflowdesignerarch.JPG "WorkflowDesignerArch")  
  
 Un oggetto <xref:System.Activities.Presentation.Model.ModelItem> è costituito da un puntatore al valore sottostante e da una raccolta di oggetti <xref:System.Activities.Presentation.Model.ModelProperty>. Un oggetto <xref:System.Activities.Presentation.Model.ModelProperty> è costituito, a sua volta, da dati quali il nome e il tipo della proprietà e quindi da un puntatore al valore che, a sua volta, è un altro <xref:System.Activities.Presentation.Model.ModelItem>. Un convertitore di valori viene usato per modificare alcuni oggetti <xref:System.Activities.Presentation.Model.ModelItem>restituiti da <xref:System.Activities.Presentation.Model.ModelProperty> in modo che siano riportati correttamente nella visualizzazione albero. Nell'esempio viene dimostrato quindi come programmare in modo imperativo rispetto all'albero <xref:System.Activities.Presentation.Model.ModelItem> usando la sintassi imperativa, come nell'esempio seguente.  
  
```csharp  
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;  
ModelProperty mp = mi.Properties["Activities"];  
mp.Collection.Add(new Persist());  
ModelItem justAdded = mp.Collection.Last();  
justAdded.Properties["DisplayName"].SetValue("new name");  
```  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire la soluzione ProgrammingModelItemTree.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compilare la soluzione selezionando **Compila soluzione** dal **compilare** menu.  
  
3.  Premere F5 per eseguire l'applicazione. Viene quindi visualizzato il form [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)].  
  
4.  Fare clic su di **carica WF** per caricare il <xref:System.Activities.Presentation.Model.ModelItem> e associarlo alla visualizzazione albero.  
  
5.  Fare clic su di **modifica albero degli elementi di modello** pulsante esegue il codice precedente per aggiungere un elemento nell'albero e impostare una proprietà.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Data.IValueConverter>
