---
title: Attività CommentOut
ms.date: 03/30/2017
ms.assetid: 340204c3-f827-45fb-870e-55e2ac457ca5
ms.openlocfilehash: 3e9f6945755bd60c551674ea8a3471a9f612da52
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43404750"
---
# <a name="commentout-activity"></a>Attività CommentOut
In questo esempio viene illustrato come scrivere un'attività personalizzata che rimuove le altre attività dal percorso di esecuzione, impostandole efficacemente come commento.  
  
## <a name="the-commentout-activity"></a>Attività CommentOut  
 Per realizzare l'obiettivo, l'attività CommentOut viene derivata dalla classe di base <xref:System.Activities.CodeActivity> e implementa un metodo <xref:System.Activities.CodeActivity.Execute%2A> vuoto.  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
}  
```  
  
 La classe viene dichiarata come illustrato nell'esempio seguente.  
  
```  
[Designer(typeof(CommentOutDesigner))]  
[ContentProperty("Body")]  
public sealed class CommentOut : CodeActivity  
```  
  
 L'attributo `Designer` specifica la classe che implementa l'interfaccia visiva dell'attività in fase di progettazione. L'attributo `ContentProperty` consente di dichiarare che è possibile ignorare la proprietà `"Body"` nella rappresentazione XAML di un'istanza di questa attività.  
  
```  
<Border x:Uid="Border_1" BorderThickness ="1">  
    <sad:WorkflowItemPresenter   
    x:Uid="sad:WorkflowItemPresenter_1" AutomationProperties.AutomationId="Body" Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
    AllowedItemType="{x:Type sa:Activity}"  
    HintText="Drop activity here"   
    Margin="5,5,5,5" />  
</Border>  
```  
  
 Nella classe della finestra di progettazione, l'XAML viene usato per creare una rappresentazione visiva personalizzata dell'attività. <xref:System.Activities.Presentation.WorkflowItemPresenter> è una classe che fornisce un editor visivo.  
  
 È possibile rilasciare una singola attività nell'area dell'attività `CommentOut`. Se si desidera aggiungere più attività a questa area, trascinarvi prima un'attività Sequence.  
  
#### <a name="to-use-this-sample"></a>Per usare questo esempio  
  
1.  Aprire CommentOut.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compilare la soluzione premendo CTRL+MAIUSC+B.  
  
3.  Avviare l'esempio senza debug premendo CTRL+F5.  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\CommentOut`
