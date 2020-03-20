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
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a><span data-ttu-id="94ccb-102">Utilizzo di ExpressionTextBox in un ActivityDesigner personalizzato</span><span class="sxs-lookup"><span data-stu-id="94ccb-102">Using the ExpressionTextBox in a Custom Activity Designer</span></span>
<span data-ttu-id="94ccb-103">In questo esempio viene illustrato come usare l'oggetto <xref:System.Activities.Presentation.View.ExpressionTextBox> in un ActivityDesigner personalizzato.</span><span class="sxs-lookup"><span data-stu-id="94ccb-103">This sample shows how to use the <xref:System.Activities.Presentation.View.ExpressionTextBox> in a custom activity designer.</span></span> <span data-ttu-id="94ccb-104">L'attività personalizzata, `MultiAssign`, assegna due valori stringa a due variabili di stringa.</span><span class="sxs-lookup"><span data-stu-id="94ccb-104">The custom activity, `MultiAssign`, assigns two string values to two string variables.</span></span> <span data-ttu-id="94ccb-105">Alcuni controlli <xref:System.Activities.Presentation.View.ExpressionTextBox> vengono associati a oggetti <xref:System.Activities.InArgument> mentre altri a oggetti <xref:System.Activities.OutArgument>.</span><span class="sxs-lookup"><span data-stu-id="94ccb-105">Some <xref:System.Activities.Presentation.View.ExpressionTextBox> controls bind to <xref:System.Activities.InArgument>s and some bind to <xref:System.Activities.OutArgument>s.</span></span>

## <a name="sample-details"></a><span data-ttu-id="94ccb-106">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="94ccb-106">Sample details</span></span>
 <span data-ttu-id="94ccb-107">L'oggetto `ArgumentToExpressionConverter` è il convertitore di tipi usato in caso di associazione di espressioni agli argomenti.</span><span class="sxs-lookup"><span data-stu-id="94ccb-107">The `ArgumentToExpressionConverter` is the type converter used when binding expressions to arguments.</span></span> <span data-ttu-id="94ccb-108">La proprietà `ConverterParameter` deve essere impostata su `In`, `Out`, a seconda delle esigenze.</span><span class="sxs-lookup"><span data-stu-id="94ccb-108">The `ConverterParameter` must be set to `In` or `Out` as appropriate.</span></span> <span data-ttu-id="94ccb-109">`InOut` non è supportata.</span><span class="sxs-lookup"><span data-stu-id="94ccb-109">`InOut` is not supported.</span></span>

 <span data-ttu-id="94ccb-110">L'attributo `UseLocationExpression` `OutArgument`viene utilizzato in s per specificare che l'espressione deve essere un'espressione di valore L ("valore sinistro" o "valore di posizione").</span><span class="sxs-lookup"><span data-stu-id="94ccb-110">The `UseLocationExpression` attribute is used on `OutArgument`s to specify that the expression should be an L-value ("left value" or "location value") expression.</span></span> <span data-ttu-id="94ccb-111">Nella maggior parte dei casi, un'espressione L-value è un identificatore di Visual Basic valido usato per indicare che l'oggetto `OutArgument` restituito è una variabile o un nome dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="94ccb-111">In most cases, an L-value expression is a valid Visual Basic identifier used to indicate that the `OutArgument` being returned is a variable or argument name.</span></span>

 <span data-ttu-id="94ccb-112">L'attributo `MaxLines` viene impostato su uno in questo esempio mentre `MinLines` non viene impostato.</span><span class="sxs-lookup"><span data-stu-id="94ccb-112">The `MaxLines` attribute is set to one in this example and `MinLines` is not set.</span></span> <span data-ttu-id="94ccb-113">Pertanto, l'oggetto <xref:System.Activities.Presentation.View.ExpressionTextBox> è una dimensione fissa di una riga, indipendentemente dalla quantità di testo digitato dall'utente.</span><span class="sxs-lookup"><span data-stu-id="94ccb-113">This indicates that the <xref:System.Activities.Presentation.View.ExpressionTextBox> is a fixed size of one line regardless of the amount of text typed by the user.</span></span> <span data-ttu-id="94ccb-114">Per consentire all'oggetto <xref:System.Activities.Presentation.View.ExpressionTextBox> di ingrandirsi per adattarsi all'input dell'utente, impostare per `MaxLines` un valore maggiore rispetto a `MinLines`.</span><span class="sxs-lookup"><span data-stu-id="94ccb-114">To allow the <xref:System.Activities.Presentation.View.ExpressionTextBox> to grow to fit user input, set `MaxLines` greater than `MinLines`.</span></span>

 <span data-ttu-id="94ccb-115">Un oggetto ExpressionTextBox può essere associato solo agli argomenti e non alle proprietà CLR.</span><span class="sxs-lookup"><span data-stu-id="94ccb-115">An ExpressionTextBox can only be bound to arguments, and cannot be bound to CLR properties.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="94ccb-116">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="94ccb-116">To use this sample</span></span>

1. <span data-ttu-id="94ccb-117">Utilizzando Visual Studio 2010, aprire il file ExpressionTextBoxSample.sln.</span><span class="sxs-lookup"><span data-stu-id="94ccb-117">Using Visual Studio 2010, open the ExpressionTextBoxSample.sln file.</span></span>

2. <span data-ttu-id="94ccb-118">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="94ccb-118">To build the solution, press CTRL+SHIFT+B.</span></span>

#### <a name="to-run-this-sample"></a><span data-ttu-id="94ccb-119">Per eseguire questo esempio</span><span class="sxs-lookup"><span data-stu-id="94ccb-119">To run this sample</span></span>

1. <span data-ttu-id="94ccb-120">Aggiungere una nuova applicazione console flusso di lavoro alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="94ccb-120">Add a new Workflow Console Application to the solution.</span></span>

2. <span data-ttu-id="94ccb-121">Aggiungere un riferimento al progetto **ExpressionTextBoxSample** dal nuovo progetto Applicazione console flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="94ccb-121">Add a reference to the **ExpressionTextBoxSample** project from the new Workflow Console Application project.</span></span>

3. <span data-ttu-id="94ccb-122">Compilare la soluzione.</span><span class="sxs-lookup"><span data-stu-id="94ccb-122">Build the solution.</span></span>

4. <span data-ttu-id="94ccb-123">Trascinare l'attività **MultiAssign** dalla casella degli strumenti e rilasciarla nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="94ccb-123">Drag the **MultiAssign** activity from the toolbox and drop it into the workflow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94ccb-124">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="94ccb-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="94ccb-125">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="94ccb-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="94ccb-126">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="94ccb-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="94ccb-127">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="94ccb-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a><span data-ttu-id="94ccb-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94ccb-128">See also</span></span>

- <xref:System.Activities.Presentation.View.ExpressionTextBox>
- [<span data-ttu-id="94ccb-129">Sviluppo di applicazioni con Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="94ccb-129">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
