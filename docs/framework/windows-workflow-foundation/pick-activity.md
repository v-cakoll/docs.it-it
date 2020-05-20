---
title: Attività di selezione
description: In Workflow Foundation, l'attività Pick semplifica la modellazione di un set di trigger di eventi seguiti dai relativi gestori corrispondenti.
ms.date: 03/30/2017
ms.assetid: b3e49b7f-0285-4720-8c09-11ae18f0d53e
ms.openlocfilehash: eb59dc20919ed2d30a48f920ad154d4b0d99c41f
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421462"
---
# <a name="pick-activity"></a><span data-ttu-id="b93b6-103">Attività di selezione</span><span class="sxs-lookup"><span data-stu-id="b93b6-103">Pick Activity</span></span>
<span data-ttu-id="b93b6-104">L'attività <xref:System.Activities.Statements.Pick> semplifica la modellazione di un set di trigger di eventi seguiti dai relativi gestori corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="b93b6-104">The <xref:System.Activities.Statements.Pick> activity simplifies the modeling of a set of event triggers followed by their corresponding handlers.</span></span>  <span data-ttu-id="b93b6-105">Un'attività <xref:System.Activities.Statements.Pick> contiene una raccolta di attività <xref:System.Activities.Statements.PickBranch> in cui ogni attività <xref:System.Activities.Statements.PickBranch> è un'associazione tra un'attività <xref:System.Activities.Statements.PickBranch.Trigger%2A> e un'attività <xref:System.Activities.Statements.PickBranch.Action%2A>.</span><span class="sxs-lookup"><span data-stu-id="b93b6-105">A <xref:System.Activities.Statements.Pick> activity contains a collection of <xref:System.Activities.Statements.PickBranch> activities, where each <xref:System.Activities.Statements.PickBranch> is a pairing between a <xref:System.Activities.Statements.PickBranch.Trigger%2A> activity and an <xref:System.Activities.Statements.PickBranch.Action%2A> activity.</span></span>  <span data-ttu-id="b93b6-106">In fase di esecuzione, i trigger per tutti i rami vengono eseguiti in parallelo.</span><span class="sxs-lookup"><span data-stu-id="b93b6-106">At execution time, the triggers for all branches are executed in parallel.</span></span>  <span data-ttu-id="b93b6-107">Quando un trigger viene completato, viene eseguita l'azione corrispondente e tutti gli altri trigger vengono annullati.</span><span class="sxs-lookup"><span data-stu-id="b93b6-107">When one trigger completes, then its corresponding action is executed, and all other triggers are canceled.</span></span>  <span data-ttu-id="b93b6-108">Il comportamento dell' [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <xref:System.Activities.Statements.Pick> attività è simile all'attività .NET Framework 3,5 <xref:System.Workflow.Activities.ListenActivity> .</span><span class="sxs-lookup"><span data-stu-id="b93b6-108">The behavior of the [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]<xref:System.Activities.Statements.Pick> activity is similar to the .NET Framework 3.5 <xref:System.Workflow.Activities.ListenActivity> activity.</span></span>  
  
 <span data-ttu-id="b93b6-109">La schermata seguente dell'esempio SDK [Utilizzo dell'attività Pick](./samples/using-the-pick-activity.md) mostra un'attività Pick con due rami.</span><span class="sxs-lookup"><span data-stu-id="b93b6-109">The following screenshot from the [Using the Pick Activity](./samples/using-the-pick-activity.md) SDK sample shows a Pick activity with two branches.</span></span>  <span data-ttu-id="b93b6-110">Un ramo dispone di un trigger denominato **Read input**, ovvero un'attività personalizzata che legge l'input dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b93b6-110">One branch has a trigger called **Read input**, a custom activity that reads input from the command line.</span></span> <span data-ttu-id="b93b6-111">L'altro ramo dispone di un trigger di attività <xref:System.Activities.Statements.Delay>.</span><span class="sxs-lookup"><span data-stu-id="b93b6-111">The second branch has a <xref:System.Activities.Statements.Delay> activity trigger.</span></span> <span data-ttu-id="b93b6-112">Se l'attività **Leggi input** riceve dati prima del <xref:System.Activities.Statements.Delay> completamento dell'attività, il <xref:System.Activities.Statements.Delay> ritardo verrà annullato e verrà scritto un messaggio di saluto nella console.</span><span class="sxs-lookup"><span data-stu-id="b93b6-112">If the **Read input** activity receives data before the <xref:System.Activities.Statements.Delay> activity finishes, <xref:System.Activities.Statements.Delay> Delay will be canceled and a greeting will be written to the console.</span></span>  <span data-ttu-id="b93b6-113">In caso contrario, se l'attività **Read input** non riceve dati nel tempo assegnato, sarà annullata e sulla console verrà scritto un messaggio di timeout.</span><span class="sxs-lookup"><span data-stu-id="b93b6-113">Otherwise, if the **Read input** activity does not receive data in the allotted time, then it will be canceled and a timeout message will be written to the console.</span></span>  <span data-ttu-id="b93b6-114">Si tratta di un modello comune usato per aggiungere un timeout a qualsiasi azione.</span><span class="sxs-lookup"><span data-stu-id="b93b6-114">This is a common pattern used to add a timeout to any action.</span></span>  
  
 ![Attività di selezione](./media/pick-activity/pick-activity-two-branches.jpg)  
  
## <a name="best-practices"></a><span data-ttu-id="b93b6-116">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="b93b6-116">Best practices</span></span>  
 <span data-ttu-id="b93b6-117">In caso di utilizzo dell'attività Pick, il ramo che viene eseguito è il ramo il cui trigger viene completato per primo.</span><span class="sxs-lookup"><span data-stu-id="b93b6-117">When using Pick, the branch that executes is the branch whose trigger completes first.</span></span>  <span data-ttu-id="b93b6-118">Concettualmente, tutti i trigger vengono eseguiti in parallelo e un trigger potrebbe aver eseguito la maggior parte della relativa logica prima che venga annullato dal completamento di un altro trigger.</span><span class="sxs-lookup"><span data-stu-id="b93b6-118">Conceptually, all triggers execute in parallel, and one trigger may have executed the majority of its logic before it is canceled by the completion of another trigger.</span></span>  <span data-ttu-id="b93b6-119">Tenuto conto di questo, quando si usa l'attività Pick è consigliabile trattare il trigger come se rappresentasse un singolo evento e inserirvi la minor quantità di logica possibile.</span><span class="sxs-lookup"><span data-stu-id="b93b6-119">With this in mind, a general guideline to follow when using the Pick activity is to treat the trigger as representing a single event, and to put as little logic as possible into it.</span></span>  <span data-ttu-id="b93b6-120">In teoria, il trigger deve contenere solo la logica necessaria per ricevere un evento e tutta l'elaborazione di tale evento deve rientrare nell'azione del ramo.</span><span class="sxs-lookup"><span data-stu-id="b93b6-120">Ideally, the trigger should contain just enough logic to receive an event, and all the processing of that event should go into the action of the branch.</span></span>  <span data-ttu-id="b93b6-121">Questo metodo riduce il numero di sovrapposizioni tra l'esecuzione dei trigger.</span><span class="sxs-lookup"><span data-stu-id="b93b6-121">This method minimizes the amount of overlap between the execution of the triggers.</span></span>  <span data-ttu-id="b93b6-122">Ad esempio si consideri un oggetto <xref:System.Activities.Statements.Pick> con due trigger in cui ogni trigger contiene un'attività <xref:System.ServiceModel.Activities.Receive> seguita da logica aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="b93b6-122">For example, consider a <xref:System.Activities.Statements.Pick> with two triggers, where each trigger contains a <xref:System.ServiceModel.Activities.Receive> activity followed by additional logic.</span></span>  <span data-ttu-id="b93b6-123">Se la logica aggiuntiva introduce un punto di inattività, entrambe le attività <xref:System.ServiceModel.Activities.Receive> potrebbero essere completate correttamente.</span><span class="sxs-lookup"><span data-stu-id="b93b6-123">If the additional logic introduces an idle point, then there is the possibility of both <xref:System.ServiceModel.Activities.Receive> activities completing successfully.</span></span>  <span data-ttu-id="b93b6-124">Un trigger sarà completato interamente, mentre un altro solo parzialmente.</span><span class="sxs-lookup"><span data-stu-id="b93b6-124">One trigger will fully complete, while another will partially complete.</span></span>  <span data-ttu-id="b93b6-125">In alcuni scenari, non è possibile accettare un messaggio e completare solo parzialmente la relativa elaborazione.</span><span class="sxs-lookup"><span data-stu-id="b93b6-125">In some scenarios, accepting a message, and then partially completing the processing of it is unacceptable.</span></span>  <span data-ttu-id="b93b6-126">Pertanto, in caso di utilizzo di attività di messaggistica incorporate in WF come <xref:System.ServiceModel.Activities.Receive> e <xref:System.ServiceModel.Activities.SendReply>, mentre l'attività <xref:System.ServiceModel.Activities.Receive> viene usata comunemente nel trigger, l'attività <xref:System.ServiceModel.Activities.SendReply> e altri tipi di logica devono essere inseriti nell'azione, se possibile.</span><span class="sxs-lookup"><span data-stu-id="b93b6-126">Therefore, when using WF built-in messaging activities such as <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply>, while <xref:System.ServiceModel.Activities.Receive> is commonly used in the trigger, <xref:System.ServiceModel.Activities.SendReply> and other logic should be put in the action whenever possible.</span></span>  
  
## <a name="using-the-pick-activity-in-the-designer"></a><span data-ttu-id="b93b6-127">Utilizzo dell'attività Pick nell'utilità di progettazione</span><span class="sxs-lookup"><span data-stu-id="b93b6-127">Using the Pick activity in the designer</span></span>  
 <span data-ttu-id="b93b6-128">Per usare l'attività Pick nell'utilità di progettazione, cercare **Pick** e **PickBranch** nella casella degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="b93b6-128">To use Pick in the designer, find **Pick** and **PickBranch** in the toolbox.</span></span>  <span data-ttu-id="b93b6-129">Trascinare l'opzione **Pick** e rilasciarla nell'area di disegno.</span><span class="sxs-lookup"><span data-stu-id="b93b6-129">Drag and drop **Pick** onto the canvas.</span></span>  <span data-ttu-id="b93b6-130">Per impostazione predefinita, una nuova attività **Pick** nell'utilità di progettazione conterrà due rami.</span><span class="sxs-lookup"><span data-stu-id="b93b6-130">By default, a new **Pick** Activity in the designer will contain two branches.</span></span>  <span data-ttu-id="b93b6-131">Per aggiungere rami aggiuntivi, trascinare l'attività **PickBranch** e rilasciarla accanto ai rami esistenti.</span><span class="sxs-lookup"><span data-stu-id="b93b6-131">To add additional branches, drag the **PickBranch** activity and drop it next to existing branches.</span></span> <span data-ttu-id="b93b6-132">Le attività possono essere rilasciate nell'area **Trigger** o nell'area **Azione** di qualsiasi **PickBranch** dell'attività **Pick**.</span><span class="sxs-lookup"><span data-stu-id="b93b6-132">Activities can be dropped onto the **Pick** Activity into either the **Trigger** area or the **Action** area of any **PickBranch**.</span></span>  
  
## <a name="using-the-pick-activity-in-code"></a><span data-ttu-id="b93b6-133">Utilizzo dell'attività Pick nel codice</span><span class="sxs-lookup"><span data-stu-id="b93b6-133">Using the Pick Activity in code</span></span>  
 <span data-ttu-id="b93b6-134">L'attività <xref:System.Activities.Statements.Pick> viene usata popolando la relativa raccolta <xref:System.Activities.Statements.Pick.Branches%2A> con le attività <xref:System.Activities.Statements.PickBranch>.</span><span class="sxs-lookup"><span data-stu-id="b93b6-134">The <xref:System.Activities.Statements.Pick> activity is used by populating its <xref:System.Activities.Statements.Pick.Branches%2A> collection with <xref:System.Activities.Statements.PickBranch> activities.</span></span> <span data-ttu-id="b93b6-135">Ognuna di queste attività <xref:System.Activities.Statements.PickBranch> dispone di una proprietà <xref:System.Activities.Statements.PickBranch.Trigger%2A> di tipo <xref:System.Activities.Activity>.</span><span class="sxs-lookup"><span data-stu-id="b93b6-135">The <xref:System.Activities.Statements.PickBranch> activities each have a <xref:System.Activities.Statements.PickBranch.Trigger%2A> property of type <xref:System.Activities.Activity>.</span></span> <span data-ttu-id="b93b6-136">Quando l'esecuzione dell'attività specificata viene completata, viene eseguita la proprietà <xref:System.Activities.Statements.PickBranch.Action%2A>.</span><span class="sxs-lookup"><span data-stu-id="b93b6-136">When the specified activity completes execution, the <xref:System.Activities.Statements.PickBranch.Action%2A> executes.</span></span>  
  
 <span data-ttu-id="b93b6-137">Nell'esempio di codice seguente viene illustrato come usare un'attività <xref:System.Activities.Statements.Pick> per implementare un timeout per un'attività che legge una riga della console.</span><span class="sxs-lookup"><span data-stu-id="b93b6-137">The following code example demonstrates how to use a <xref:System.Activities.Statements.Pick> activity to implement a timeout for an activity that reads a line from the console.</span></span>  
  
```csharp  
Sequence body = new Sequence()  
{  
    Variables = { name },  
    Activities =
   {  
       new System.Activities.Statements.Pick  
        {  
           Branches =
           {  
               new PickBranch  
               {  
                   Trigger = new ReadLine  
                   {  
                      Result = name,  
                      BookmarkName = "name"  
                   },  
                   Action = new WriteLine
                   {
                       Text = ExpressionServices.Convert<string>(ctx => "Hello " +
                           name.Get(ctx))
                   }  
               },  
               new PickBranch  
               {  
                   Trigger = new Delay  
                   {  
                      Duration = new TimeSpan(0, 0, 5)  
                   },  
                   Action = new WriteLine  
                   {  
                      Text = "Time is up."  
                   }  
               }  
           }  
       }  
   }  
};  
```  
  
```xaml  
<Sequence xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <Variable x:TypeArguments="x:String" Name="username" />  
  </Sequence.Variables>  
  <Pick>  
    <PickBranch>  
      <PickBranch.Trigger>  
        <ReadLine BookmarkName="name" Result="username" />  
      </PickBranch.Trigger>  
      <WriteLine>[String.Concat("Hello ", username)]</WriteLine>  
    </PickBranch>  
    <PickBranch>  
      <PickBranch.Trigger>  
        <Delay>00:00:05</Delay>  
      </PickBranch.Trigger>  
      <WriteLine>Time is up.</WriteLine>  
    </PickBranch>  
  </Pick>  
</Sequence>  
```
