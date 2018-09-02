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
# <a name="commentout-activity"></a><span data-ttu-id="ed644-102">Attività CommentOut</span><span class="sxs-lookup"><span data-stu-id="ed644-102">CommentOut Activity</span></span>
<span data-ttu-id="ed644-103">In questo esempio viene illustrato come scrivere un'attività personalizzata che rimuove le altre attività dal percorso di esecuzione, impostandole efficacemente come commento.</span><span class="sxs-lookup"><span data-stu-id="ed644-103">This sample demonstrates how to write a custom activity that removes other activities from the path of execution, effectively commenting them out.</span></span>  
  
## <a name="the-commentout-activity"></a><span data-ttu-id="ed644-104">Attività CommentOut</span><span class="sxs-lookup"><span data-stu-id="ed644-104">The CommentOut Activity</span></span>  
 <span data-ttu-id="ed644-105">Per realizzare l'obiettivo, l'attività CommentOut viene derivata dalla classe di base <xref:System.Activities.CodeActivity> e implementa un metodo <xref:System.Activities.CodeActivity.Execute%2A> vuoto.</span><span class="sxs-lookup"><span data-stu-id="ed644-105">To achieve its goal, the CommentOut activity derives from the <xref:System.Activities.CodeActivity> base class and implements an empty <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
}  
```  
  
 <span data-ttu-id="ed644-106">La classe viene dichiarata come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="ed644-106">The class is declared as shown in the following example.</span></span>  
  
```  
[Designer(typeof(CommentOutDesigner))]  
[ContentProperty("Body")]  
public sealed class CommentOut : CodeActivity  
```  
  
 <span data-ttu-id="ed644-107">L'attributo `Designer` specifica la classe che implementa l'interfaccia visiva dell'attività in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="ed644-107">The `Designer` attribute specifies the class that implements the visual interface of the activity at design time.</span></span> <span data-ttu-id="ed644-108">L'attributo `ContentProperty` consente di dichiarare che è possibile ignorare la proprietà `"Body"` nella rappresentazione XAML di un'istanza di questa attività.</span><span class="sxs-lookup"><span data-stu-id="ed644-108">The `ContentProperty` attribute declares that the `"Body"` property can be skipped in the XAML representation of an instance of this activity.</span></span>  
  
```  
<Border x:Uid="Border_1" BorderThickness ="1">  
    <sad:WorkflowItemPresenter   
    x:Uid="sad:WorkflowItemPresenter_1" AutomationProperties.AutomationId="Body" Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
    AllowedItemType="{x:Type sa:Activity}"  
    HintText="Drop activity here"   
    Margin="5,5,5,5" />  
</Border>  
```  
  
 <span data-ttu-id="ed644-109">Nella classe della finestra di progettazione, l'XAML viene usato per creare una rappresentazione visiva personalizzata dell'attività.</span><span class="sxs-lookup"><span data-stu-id="ed644-109">In the designer class, XAML is used to create a custom visual representation of the activity.</span></span> <span data-ttu-id="ed644-110"><xref:System.Activities.Presentation.WorkflowItemPresenter> è una classe che fornisce un editor visivo.</span><span class="sxs-lookup"><span data-stu-id="ed644-110"><xref:System.Activities.Presentation.WorkflowItemPresenter> is a class that provides the visual editor.</span></span>  
  
 <span data-ttu-id="ed644-111">È possibile rilasciare una singola attività nell'area dell'attività `CommentOut`.</span><span class="sxs-lookup"><span data-stu-id="ed644-111">A single activity can be dropped onto the `CommentOut` activity surface.</span></span> <span data-ttu-id="ed644-112">Se si desidera aggiungere più attività a questa area, trascinarvi prima un'attività Sequence.</span><span class="sxs-lookup"><span data-stu-id="ed644-112">If you want to add multiple activities to this surface, drag a sequence activity here first.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ed644-113">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="ed644-113">To use this sample</span></span>  
  
1.  <span data-ttu-id="ed644-114">Aprire CommentOut.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed644-114">Open CommentOut.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ed644-115">Compilare la soluzione premendo CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="ed644-115">Compile the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ed644-116">Avviare l'esempio senza debug premendo CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="ed644-116">Start the sample without debugging by pressing CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ed644-117">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="ed644-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ed644-118">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="ed644-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ed644-119">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="ed644-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ed644-120">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="ed644-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\CommentOut`
