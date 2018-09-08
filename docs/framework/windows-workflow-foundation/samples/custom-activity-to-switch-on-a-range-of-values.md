---
title: Attività personalizzata per il passaggio in base a un intervallo di valori
ms.date: 03/30/2017
ms.assetid: 441e0a17-421f-430c-ba97-59e4cc6c88e3
ms.openlocfilehash: cfaf4318b1557a9fc217de8254e164243ea54569
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44195306"
---
# <a name="custom-activity-to-switch-on-a-range-of-values"></a><span data-ttu-id="f81de-102">Attività personalizzata per il passaggio in base a un intervallo di valori</span><span class="sxs-lookup"><span data-stu-id="f81de-102">Custom Activity to Switch on a Range of Values</span></span>
<span data-ttu-id="f81de-103">In questo esempio viene illustrato come creare un'attività personalizzata che estende l'uso di <xref:System.Activities.Statements.Switch%601>.</span><span class="sxs-lookup"><span data-stu-id="f81de-103">This sample demonstrates how to create a custom activity that extends the use of a <xref:System.Activities.Statements.Switch%601>.</span></span> <span data-ttu-id="f81de-104">Un'istruzione <xref:System.Activities.Statements.Switch%601> convenzionale consente il passaggio in base a un singolo valore.</span><span class="sxs-lookup"><span data-stu-id="f81de-104">A conventional <xref:System.Activities.Statements.Switch%601> statement allows switching based upon a single value.</span></span> <span data-ttu-id="f81de-105">Esistono tuttavia scenari aziendali in cui il passaggio di un'attività deve basarsi su un intervallo di valori.</span><span class="sxs-lookup"><span data-stu-id="f81de-105">But, there are business scenarios where an activity must switch based upon a range of values.</span></span> <span data-ttu-id="f81de-106">Ad esempio, un'attività potrebbe eseguire un'azione quando il valore su cui si basa il passaggio è compreso tra 1 e 5, un'altra azione quando il valore è compreso tra 6 e 10 e un'azione predefinita per tutti gli altri valori.</span><span class="sxs-lookup"><span data-stu-id="f81de-106">For example, an activity might execute one action when the value being switched upon is between 1 and 5, another action when the value is between 6 and 10, and a default action for all other values.</span></span> <span data-ttu-id="f81de-107">Questa attività personalizzata abilita esattamente tale scenario.</span><span class="sxs-lookup"><span data-stu-id="f81de-107">This custom activity enables exactly that scenario.</span></span>  
  
## <a name="the-switchrange-activity"></a><span data-ttu-id="f81de-108">Attività SwitchRange</span><span class="sxs-lookup"><span data-stu-id="f81de-108">The SwitchRange Activity</span></span>  
 <span data-ttu-id="f81de-109">Tramite l'attività `SwitchRange` viene pianificata un'attività figlio quando il valore restituito dall'espressione è incluso nell'intervallo di uno dei relativi `Cases`.</span><span class="sxs-lookup"><span data-stu-id="f81de-109">The `SwitchRange` activity schedules a child activity when the result value of its expression is included within the range of one of its `Cases`.</span></span>  
  
 <span data-ttu-id="f81de-110">L'esempio di codice seguente è un'attività personalizzata il cui passaggio si basa su un intervallo di valori.</span><span class="sxs-lookup"><span data-stu-id="f81de-110">The following code example is a custom activity that switches based upon a range of values.</span></span>  
  
```csharp  
public sealed class SwitchRange<T> : NativeActivity where T : IComparable  
{  
   [RequiredArgument]  
   [DefaultValue(null)]  
   public InArgument<T> Expression { get; set; }  
  
   public IList<CaseRange<T>> Cases  
  
   [DefaultValue(null)]  
   public Activity Default { get; set; }}  
}  
```  
  
|<span data-ttu-id="f81de-111">Proprietà</span><span class="sxs-lookup"><span data-stu-id="f81de-111">Property</span></span>|<span data-ttu-id="f81de-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f81de-112">Description</span></span>|  
|-|-|  
|<span data-ttu-id="f81de-113">Expression</span><span class="sxs-lookup"><span data-stu-id="f81de-113">Expression</span></span>|<span data-ttu-id="f81de-114">Si tratta dell'espressione da valutare e confrontare rispetto agli intervalli nell'elenco Cases.</span><span class="sxs-lookup"><span data-stu-id="f81de-114">This is the expression to be evaluated and compared against the ranges in the Cases list.</span></span> <span data-ttu-id="f81de-115">Il risultato dell'espressione è di tipo T.</span><span class="sxs-lookup"><span data-stu-id="f81de-115">The result of the expression is of type T.</span></span>|  
|<span data-ttu-id="f81de-116">Cases</span><span class="sxs-lookup"><span data-stu-id="f81de-116">Cases</span></span>|<span data-ttu-id="f81de-117">Ogni caso è costituito da un intervallo (Da e A) e da un'attività (Body).</span><span class="sxs-lookup"><span data-stu-id="f81de-117">Each case consists of a range (From and To) and an activity (Body).</span></span> <span data-ttu-id="f81de-118">L'espressione viene valutata e confrontata rispetto agli intervalli.</span><span class="sxs-lookup"><span data-stu-id="f81de-118">The expression is evaluated and compared against the ranges.</span></span> <span data-ttu-id="f81de-119">Se il risultato dell'espressione è compreso nell'intervallo di uno dei casi, viene eseguita l'attività corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f81de-119">If the result of the expression is within the range of one of the cases, the corresponding activity is executed.</span></span>|  
|<span data-ttu-id="f81de-120">Default</span><span class="sxs-lookup"><span data-stu-id="f81de-120">Default</span></span>|<span data-ttu-id="f81de-121">L'attività che viene eseguita quando nessun caso corrisponde.</span><span class="sxs-lookup"><span data-stu-id="f81de-121">The activity that is executed when no case is matched.</span></span> <span data-ttu-id="f81de-122">Quando è impostata su `null`, non viene eseguita alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="f81de-122">When set to `null`, no action is taken.</span></span>|  
  
## <a name="caserange-class"></a><span data-ttu-id="f81de-123">Classe CaseRange</span><span class="sxs-lookup"><span data-stu-id="f81de-123">CaseRange Class</span></span>  
 <span data-ttu-id="f81de-124">La classe `CaseRange` rappresenta un intervallo all'interno di un'attività `SwitchRange`.</span><span class="sxs-lookup"><span data-stu-id="f81de-124">The `CaseRange` class represents a range within a `SwitchRange` activity.</span></span> <span data-ttu-id="f81de-125">Ogni istanza di `CaseRange` contiene un intervallo (costituito da un oggetto `From` e un oggetto `To`) e un'attività `Body` che viene pianificata se l'espressione in `SwitchRange` viene valutata all'interno dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="f81de-125">Every instance of `CaseRange` contains a range (composed of a `From` and a `To`) and a `Body` activity that is scheduled if the expression in the `SwitchRange` is evaluated within the range.</span></span>  
  
 <span data-ttu-id="f81de-126">L'esempio di codice riportato di seguito è la definizione per la classe `CaseRange`.</span><span class="sxs-lookup"><span data-stu-id="f81de-126">The following code example is the definition for the `CaseRange` class.</span></span>  
  
```  
public class CaseRange<T> where T : IComparable  
{  
    public T From { get; set; }  
  
    public T To { get; set; }  
  
    public Activity Action { get; set; }  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="f81de-127">Entrambe le classi `SwitchRange` e `CaseRange`, definite nell'esempio, sono classi generiche che possono essere usate con qualsiasi tipo che implementa `IComparable`, come la classe <xref:System.Activities.Statements.Switch%601>.</span><span class="sxs-lookup"><span data-stu-id="f81de-127">Both the `SwitchRange` and `CaseRange` classes, which are defined in the sample are generic classes that can work with any type that implements `IComparable`, like the <xref:System.Activities.Statements.Switch%601> class.</span></span>  
  
## <a name="sample-usage"></a><span data-ttu-id="f81de-128">Utilizzo dell'esempio</span><span class="sxs-lookup"><span data-stu-id="f81de-128">Sample Usage</span></span>  
 <span data-ttu-id="f81de-129">Nell'esempio di codice seguente viene illustrato come usare l'attività `SwitchRange`.</span><span class="sxs-lookup"><span data-stu-id="f81de-129">The following code example demonstrates how to use the `SwitchRange` activity.</span></span>  
  
```csharp  
Activity SwitchRange = new SwitchRange<int>  
{  
    Expression = new InArgument<int>(value),  
    Cases =   
    {  
        new CaseRange<int>                      
        {  
            From = 1,  
            To = 5,  
            Action = new WriteLine  
            {  
                Text = "Case 1-5 selected",  
            }  
        },  
        new CaseRange<int>  
        {  
            From = 6,  
            To = 10,  
            Action = new WriteLine  
            {  
                Text = "Case 6-10 selected",  
            }  
        }  
    },  
    Default = new WriteLine { Text = "Default Case selected" }  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f81de-130">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="f81de-130">To use this sample</span></span>  
  
1.  <span data-ttu-id="f81de-131">Tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione SwitchRange.sln.</span><span class="sxs-lookup"><span data-stu-id="f81de-131">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the SwitchRange.sln solution file.</span></span>  
  
2.  <span data-ttu-id="f81de-132">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="f81de-132">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="f81de-133">Per eseguire la soluzione, premere CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="f81de-133">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f81de-134">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="f81de-134">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f81de-135">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="f81de-135">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f81de-136">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="f81de-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f81de-137">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="f81de-137">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SwitchRange`