---
title: "Utilizzo dell'attività di interoperabilità in un flusso di lavoro di .NET Framework 4"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aa8bb873ed42d5ba717359f420855b605cbe423d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-interop-activity-in-a-net-framework-4-workflow"></a><span data-ttu-id="b2f10-102">Utilizzo dell'attività di interoperabilità in un flusso di lavoro di .NET Framework 4</span><span class="sxs-lookup"><span data-stu-id="b2f10-102">Using the Interop Activity in a .NET Framework 4 Workflow</span></span>
<span data-ttu-id="b2f10-103">Le attività create tramite [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] o [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] possono essere usate nel flusso di lavoro di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] mediante l'attività <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="b2f10-103">Activities created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] or [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] can be used in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow by using the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="b2f10-104">In questo argomento viene fornita una panoramica sull'utilizzo dell'attività <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="b2f10-104">This topic provides an overview of using the <xref:System.Activities.Statements.Interop> activity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2f10-105">Il <xref:System.Activities.Statements.Interop> attività non viene visualizzato nella casella degli strumenti della finestra di progettazione del flusso di lavoro a meno che non dispone di progetto del flusso di lavoro relativo **Framework di destinazione** impostazione **.Net Framework 4** o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="b2f10-105">The <xref:System.Activities.Statements.Interop> activity does not appear in the workflow designer toolbox unless the workflow's project has its **Target Framework** setting set to **.Net Framework 4** or later.</span></span>  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a><span data-ttu-id="b2f10-106">Utilizzo dell'attività di interoperabilità nei flussi di lavoro di .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b2f10-106">Using the Interop Activity in .NET Framework 4.5 Workflows</span></span>  
 <span data-ttu-id="b2f10-107">In questo argomento viene creata una libreria di attività di [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] contenente un'attività `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="b2f10-107">In this topic, a [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity library is created that contains a `DiscountCalculator` activity.</span></span> <span data-ttu-id="b2f10-108">`DiscountCalculator` consente di calcolare uno sconto in base a un importo di acquisto ed è costituita da un oggetto <xref:System.Workflow.Activities.SequenceActivity> contenente un oggetto <xref:System.Workflow.Activities.PolicyActivity>.</span><span class="sxs-lookup"><span data-stu-id="b2f10-108">The `DiscountCalculator` calculates a discount based on a purchase amount and consists of a <xref:System.Workflow.Activities.SequenceActivity> that contains a <xref:System.Workflow.Activities.PolicyActivity>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2f10-109">L'attività di [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] creata in questo argomento usa un oggetto <xref:System.Workflow.Activities.PolicyActivity> per implementare la logica dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b2f10-109">The [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity created in this topic uses a <xref:System.Workflow.Activities.PolicyActivity> to implement the logic of the activity.</span></span> <span data-ttu-id="b2f10-110">Non è necessario usare un'attività [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] personalizzata o l'attività <xref:System.Activities.Statements.Interop> per sfruttare le regole in un flusso di lavoro di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2f10-110">It is not required to use a custom [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] activity or the <xref:System.Activities.Statements.Interop> activity in order to use rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow.</span></span> <span data-ttu-id="b2f10-111">Per un esempio di utilizzo di regole in un [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] flusso di lavoro senza utilizzare il <xref:System.Activities.Statements.Interop> attività, vedere il [attività Policy in .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="b2f10-111">For an example of using rules in a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow without using the <xref:System.Activities.Statements.Interop> activity, see the [Policy Activity in .NET Framework 4.5](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) sample.</span></span>  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a><span data-ttu-id="b2f10-112">Per creare il progetto della libreria di attività di .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="b2f10-112">To create the .NET Framework 3.5 activity library project</span></span>  
  
1.  <span data-ttu-id="b2f10-113">Aprire [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] e selezionare **New** e quindi **progetto...**</span><span class="sxs-lookup"><span data-stu-id="b2f10-113">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and select **New** and then **Project…**</span></span> <span data-ttu-id="b2f10-114">dal **File** menu.</span><span class="sxs-lookup"><span data-stu-id="b2f10-114">from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="b2f10-115">Espandere il **altri tipi di progetto** nodo il **modelli installati** riquadro e selezionare **soluzioni di Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-115">Expand the **Other Project Types** node in the **Installed Templates** pane and select **Visual Studio Solutions**.</span></span>  
  
3.  <span data-ttu-id="b2f10-116">Selezionare **soluzione vuota** dal **soluzioni di Visual Studio** elenco.</span><span class="sxs-lookup"><span data-stu-id="b2f10-116">Select **Blank Solution** from the **Visual Studio Solutions** list.</span></span> <span data-ttu-id="b2f10-117">Tipo `PolicyInteropDemo` nel **nome** casella e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-117">Type `PolicyInteropDemo` in the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="b2f10-118">Fare doppio clic su **PolicyInteropDemo** in **Esplora** e selezionare **Aggiungi** e quindi **nuovo progetto...** .</span><span class="sxs-lookup"><span data-stu-id="b2f10-118">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add** and then **New Project…**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b2f10-119">Se il **Esplora** finestra non è visibile, selezionare **Esplora** dal **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="b2f10-119">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="b2f10-120">Nel **modelli installati** elenco, selezionare **Visual c#** e quindi **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-120">In the **Installed Templates** list, select **Visual C#** and then **Workflow**.</span></span> <span data-ttu-id="b2f10-121">Selezionare **.NET Framework 3.5** dall'elenco a discesa versione .NET Framework e quindi selezionare **Workflow Activity Library** dal **modelli** elenco.</span><span class="sxs-lookup"><span data-stu-id="b2f10-121">Select **.NET Framework 3.5** from the .NET Framework version drop-down list, and then select **Workflow Activity Library** from the **Templates** list.</span></span>  
  
6.  <span data-ttu-id="b2f10-122">Tipo `PolicyActivityLibrary` nel **nome** casella e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-122">Type `PolicyActivityLibrary` in the **Name** box and click **OK**.</span></span>  
  
7.  <span data-ttu-id="b2f10-123">Fare doppio clic su **Activity1. cs** in **Esplora** e selezionare **eliminare**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-123">Right-click **Activity1.cs** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="b2f10-124">Per confermare scegliere **OK** .</span><span class="sxs-lookup"><span data-stu-id="b2f10-124">Click **OK** to confirm.</span></span>  
  
#### <a name="to-create-the-discountcalculator-activity"></a><span data-ttu-id="b2f10-125">Per creare l'attività DiscountCalculator</span><span class="sxs-lookup"><span data-stu-id="b2f10-125">To create the DiscountCalculator activity</span></span>  
  
1.  <span data-ttu-id="b2f10-126">Fare doppio clic su **PolicyActivityLibrary** in **Esplora** e selezionare **Aggiungi** e quindi **attività...** .</span><span class="sxs-lookup"><span data-stu-id="b2f10-126">Right-click **PolicyActivityLibrary** in **Solution Explorer** and select **Add** and then **Activity…**.</span></span>  
  
2.  <span data-ttu-id="b2f10-127">Selezionare **attività (con separazione del codice)** dal **elementi di Visual c#** elenco.</span><span class="sxs-lookup"><span data-stu-id="b2f10-127">Select **Activity (with code separation)** from the **Visual C# Items** list.</span></span> <span data-ttu-id="b2f10-128">Tipo `DiscountCalculator` nel **nome** casella e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-128">Type `DiscountCalculator` in the **Name** box and click **OK**.</span></span>  
  
3.  <span data-ttu-id="b2f10-129">Fare doppio clic su **Discountcalculator** in **Esplora** e selezionare **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-129">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Code**.</span></span>  
  
4.  <span data-ttu-id="b2f10-130">Aggiungere le tre seguenti proprietà alla classe `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="b2f10-130">Add the following three properties to the `DiscountCalculator` class.</span></span>  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  <span data-ttu-id="b2f10-131">Fare doppio clic su **Discountcalculator** in **Esplora** e selezionare **Visualizza finestra di progettazione**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-131">Right-click **DiscountCalculator.xoml** in **Solution Explorer** and select **View Designer**.</span></span>  
  
6.  <span data-ttu-id="b2f10-132">Trascinare un **criteri** attività dal **Windows Workflow v 3.0** sezione il **della casella degli strumenti** e rilasciarlo nel **DiscountCalculator** attività .</span><span class="sxs-lookup"><span data-stu-id="b2f10-132">Drag a **Policy** activity from the **Windows Workflow v3.0** section of the **Toolbox** and drop it in the **DiscountCalculator** activity.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b2f10-133">Se il **della casella degli strumenti** finestra non è visibile, selezionare **della casella degli strumenti** dal **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="b2f10-133">If the **Toolbox** window is not visible, select **Toolbox** from the **View** menu.</span></span>  
  
#### <a name="to-configure-the-rules"></a><span data-ttu-id="b2f10-134">Per configurare le regole</span><span class="sxs-lookup"><span data-stu-id="b2f10-134">To configure the rules</span></span>  
  
1.  <span data-ttu-id="b2f10-135">Fare clic su appena aggiunta **criteri** attività per selezionarlo, se non è già selezionato.</span><span class="sxs-lookup"><span data-stu-id="b2f10-135">Click the newly added **Policy** activity to select it, if it is not already selected.</span></span>  
  
2.  <span data-ttu-id="b2f10-136">Fare clic su di **RuleSetReference** proprietà il **proprietà** finestra per selezionarla e fare clic sul pulsante con i puntini di sospensione a destra della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b2f10-136">Click the **RuleSetReference** property in the **Properties** window to select it, and click the ellipsis button to the right of the property.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b2f10-137">Se il **proprietà** finestra non è visibile, scegliere **finestra proprietà** dal **vista** menu.</span><span class="sxs-lookup"><span data-stu-id="b2f10-137">If the **Properties** window is not visible, choose **Properties Window** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="b2f10-138">Selezionare **fare clic su nuovo...** .</span><span class="sxs-lookup"><span data-stu-id="b2f10-138">Select **Click New…**.</span></span>  
  
4.  <span data-ttu-id="b2f10-139">Fare clic su **Aggiungi regola**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-139">Click **Add Rule**.</span></span>  
  
5.  <span data-ttu-id="b2f10-140">Digitare l'espressione seguente nella **condizione** casella.</span><span class="sxs-lookup"><span data-stu-id="b2f10-140">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  <span data-ttu-id="b2f10-141">Digitare l'espressione seguente nella **azioni Then** casella.</span><span class="sxs-lookup"><span data-stu-id="b2f10-141">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  <span data-ttu-id="b2f10-142">Fare clic su **Aggiungi regola**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-142">Click **Add Rule**.</span></span>  
  
8.  <span data-ttu-id="b2f10-143">Digitare l'espressione seguente nella **condizione** casella.</span><span class="sxs-lookup"><span data-stu-id="b2f10-143">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. <span data-ttu-id="b2f10-144">Digitare l'espressione seguente nella **azioni Then** casella.</span><span class="sxs-lookup"><span data-stu-id="b2f10-144">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. <span data-ttu-id="b2f10-145">Fare clic su **Aggiungi regola**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-145">Click **Add Rule**.</span></span>  
  
11. <span data-ttu-id="b2f10-146">Digitare l'espressione seguente nella **condizione** casella.</span><span class="sxs-lookup"><span data-stu-id="b2f10-146">Type the following expression into the **Condition** box.</span></span>  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. <span data-ttu-id="b2f10-147">Digitare l'espressione seguente nella **azioni Then** casella.</span><span class="sxs-lookup"><span data-stu-id="b2f10-147">Type the following expression into the **Then Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. <span data-ttu-id="b2f10-148">Digitare l'espressione seguente nella **azioni Else** casella.</span><span class="sxs-lookup"><span data-stu-id="b2f10-148">Type the following expression into the **Else Actions** box.</span></span>  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. <span data-ttu-id="b2f10-149">Fare clic su **OK** per chiudere la **Editor Set di regole** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b2f10-149">Click **OK** to close the **Rule Set Editor** dialog box.</span></span>  
  
15. <span data-ttu-id="b2f10-150">Verificare che il nuovo <xref:System.Workflow.Activities.Rules.RuleSet> è selezionata nel **nome** elenco e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-150">Ensure that the newly-created <xref:System.Workflow.Activities.Rules.RuleSet> is selected in the **Name** list, and click **OK**.</span></span>  
  
16. <span data-ttu-id="b2f10-151">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="b2f10-151">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
 <span data-ttu-id="b2f10-152">Le regole aggiunte all'attività `DiscountCalculator` in questa procedura vengono mostrate nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b2f10-152">The rules added to the `DiscountCalculator` activity in this procedure are shown in the following code example.</span></span>  
  
```  
Rule1: IF this.Subtotal >= 50 && this.Subtotal < 100   
       THEN this.DiscountPercent = 0.075   
  
Rule2: IF this. Subtotal >= 100   
       THEN this.DiscountPercent = 0.15   
  
Rule3: IF this.DiscountPercent > 0   
       THEN this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent   
       ELSE this.Total = this.Subtotal  
```  
  
 <span data-ttu-id="b2f10-153">Quando l'oggetto <xref:System.Workflow.Activities.PolicyActivity> viene eseguito, queste tre regole valutano e modificano i valori delle proprietà `Subtotal`, `DiscountPercent` e `Total` dell'attività `DiscountCalculator` per calcolare lo sconto desiderato.</span><span class="sxs-lookup"><span data-stu-id="b2f10-153">When the <xref:System.Workflow.Activities.PolicyActivity> executes, these three rules evaluate and modify the `Subtotal`, `DiscountPercent`, and `Total` property values of the `DiscountCalculator` activity to calculate the desired discount.</span></span>  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a><span data-ttu-id="b2f10-154">Utilizzo dell'attività DiscountCalculator con l'attività di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="b2f10-154">Using the DiscountCalculator Activity with the Interop Activity</span></span>  
 <span data-ttu-id="b2f10-155">Per usare l'attività `DiscountCalculator` in un flusso di lavoro di [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], viene usata l'attività <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="b2f10-155">To use the `DiscountCalculator` activity inside a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow, the <xref:System.Activities.Statements.Interop> activity is used.</span></span> <span data-ttu-id="b2f10-156">Contenuto della sezione vengono creati due flussi di lavoro (in uno viene usato il codice e nell'altro la relativa utilità di progettazione) che illustrano come usare l'attività <xref:System.Activities.Statements.Interop> con l'attività `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="b2f10-156">In this section two workflows are created, one using code and one using the workflow designer, which show how to use the <xref:System.Activities.Statements.Interop> activity with the `DiscountCalculator` activity.</span></span> <span data-ttu-id="b2f10-157">In entrambi i flussi di lavoro viene usata la stessa applicazione host.</span><span class="sxs-lookup"><span data-stu-id="b2f10-157">The same host application is used for both workflows.</span></span>  
  
#### <a name="to-create-the-host-application"></a><span data-ttu-id="b2f10-158">Per creare l'applicazione host</span><span class="sxs-lookup"><span data-stu-id="b2f10-158">To create the host application</span></span>  
  
1.  <span data-ttu-id="b2f10-159">Fare doppio clic su **PolicyInteropDemo** in **Esplora** e selezionare **Aggiungi**e quindi **nuovo progetto...** .</span><span class="sxs-lookup"><span data-stu-id="b2f10-159">Right-click **PolicyInteropDemo** in **Solution Explorer** and select **Add**, and then **New Project…**.</span></span>  
  
2.  <span data-ttu-id="b2f10-160">Verificare che **.NET Framework 4.5** sia selezionata nell'elenco a discesa versione di .NET Framework e selezionare **applicazione Console flusso di lavoro** dal **elementi di Visual c#** elenco.</span><span class="sxs-lookup"><span data-stu-id="b2f10-160">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list, and select  **Workflow Console Application** from the **Visual C# Items** list.</span></span>  
  
3.  <span data-ttu-id="b2f10-161">Tipo `PolicyInteropHost` nel **nome** casella e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-161">Type `PolicyInteropHost` into the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="b2f10-162">Fare doppio clic su **PolicyInteropHost** in **Esplora** e selezionare **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-162">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="b2f10-163">Nel **framework di destinazione** elenco a discesa elenco, modificare la selezione da **.NET Framework 4 Client Profile** a **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-163">In the **Target framework** drop-down list, change the selection from **.NET Framework 4 Client Profile** to **.NET Framework 4.5**.</span></span> <span data-ttu-id="b2f10-164">Fare clic su **Sì** per confermare.</span><span class="sxs-lookup"><span data-stu-id="b2f10-164">Click **Yes** to confirm.</span></span>  
  
6.  <span data-ttu-id="b2f10-165">Fare doppio clic su **PolicyInteropHost** in **Esplora** e selezionare **Aggiungi riferimento...** .</span><span class="sxs-lookup"><span data-stu-id="b2f10-165">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
7.  <span data-ttu-id="b2f10-166">Selezionare **PolicyActivityLibrary** dal **progetti** scheda e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-166">Select **PolicyActivityLibrary** from the **Projects** tab and click **OK**.</span></span>  
  
8.  <span data-ttu-id="b2f10-167">Fare doppio clic su **PolicyInteropHost** in **Esplora** e selezionare **Aggiungi riferimento...** .</span><span class="sxs-lookup"><span data-stu-id="b2f10-167">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add Reference…**.</span></span>  
  
9. <span data-ttu-id="b2f10-168">Selezionare **System.Workflow.Activities**, **ComponentModel**e quindi **System.Workflow.Runtime** dal **.NET**scheda e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-168">Select **System.Workflow.Activities**, **System.Workflow.ComponentModel**, and then **System.Workflow.Runtime** from the **.NET** tab and click **OK**.</span></span>  
  
10. <span data-ttu-id="b2f10-169">Fare doppio clic su **PolicyInteropHost** in **Esplora** e selezionare **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-169">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>  
  
11. <span data-ttu-id="b2f10-170">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="b2f10-170">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
### <a name="using-the-interop-activity-in-code"></a><span data-ttu-id="b2f10-171">Utilizzo dell'attività di interoperabilità nel codice</span><span class="sxs-lookup"><span data-stu-id="b2f10-171">Using the Interop Activity in Code</span></span>  
 <span data-ttu-id="b2f10-172">In questo esempio viene creata una definizione di flusso di lavoro tramite il codice contenente le attività <xref:System.Activities.Statements.Interop> e `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="b2f10-172">In this example, a workflow definition is created using code that contains the <xref:System.Activities.Statements.Interop> activity and the `DiscountCalculator` activity.</span></span> <span data-ttu-id="b2f10-173">Questo flusso di lavoro viene richiamato usando l'oggetto <xref:System.Activities.WorkflowInvoker> e i risultati della valutazione della regola vengono scritti nella console tramite un'attività <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="b2f10-173">This workflow is invoked using <xref:System.Activities.WorkflowInvoker> and the results of the rule evaluation are written to the console using a <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
##### <a name="to-use-the-interop-activity-in-code"></a><span data-ttu-id="b2f10-174">Per usare l'attività di interoperabilità nel codice</span><span class="sxs-lookup"><span data-stu-id="b2f10-174">To use the Interop activity in code</span></span>  
  
1.  <span data-ttu-id="b2f10-175">Fare doppio clic su **Program.cs** in **Esplora** e selezionare **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-175">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
2.  <span data-ttu-id="b2f10-176">Aggiungere la seguente istruzione `using` all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="b2f10-176">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using PolicyActivityLibrary;  
    ```  
  
3.  <span data-ttu-id="b2f10-177">Rimuovere il contenuto del metodo `Main` e sostituirlo con il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="b2f10-177">Remove the contents of the `Main` method and replace with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
4.  <span data-ttu-id="b2f10-178">Creare un nuovo metodo nella classe `Program` denominato `CalculateDiscountUsingCodeWorkflow` contenente il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b2f10-178">Create a new method in the `Program` class called `CalculateDiscountUsingCodeWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingCodeWorkflow()  
    {  
        Variable<double> Subtotal = new Variable<double>  
        {  
            Default = 75.99,  
            Name = "Subtotal"  
        };  
  
        Variable<double> DiscountPercent = new Variable<double>  
        {  
            Name = "DiscountPercent"  
        };  
  
        Variable<double> Total = new Variable<double>  
        {  
            Name = "Total"  
        };  
  
        Activity wf = new Sequence  
        {  
            Variables = { Subtotal, DiscountPercent, Total },  
            Activities =   
            {  
                new Interop  
                {  
                    ActivityType = typeof(DiscountCalculator),  
                    ActivityProperties =   
                    {  
                        { "Subtotal", new InArgument<double>(Subtotal) },  
                        { "DiscountPercentOut", new OutArgument<double>(DiscountPercent) },  
                        { "TotalOut", new OutArgument<double>(Total) }  
                    }  
                },  
                new WriteLine  
                {  
                    Text =  new InArgument<string>(env =>   
                        string.Format("Subtotal: {0:C}, Discount {1}%, Total {2:C}",   
                        Subtotal.Get(env), DiscountPercent.Get(env) * 100, Total.Get(env)))  
                }  
            }  
        };  
  
        WorkflowInvoker.Invoke(wf);  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b2f10-179">Le proprietà `Subtotal`, `DiscountPercent` e `Total` dell'attività `DiscountCalculator` vengono rilevate come argomenti dell'attività <xref:System.Activities.Statements.Interop> e associate a variabili del flusso di lavoro locali nella raccolta <xref:System.Activities.Statements.Interop> dell'attività <xref:System.Activities.Statements.Interop.ActivityProperties%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2f10-179">The `Subtotal`, `DiscountPercent`, and `Total` properties of the `DiscountCalculator` activity are surfaced as arguments of the <xref:System.Activities.Statements.Interop> activity, and bound to local workflow variables in the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityProperties%2A> collection.</span></span> <span data-ttu-id="b2f10-180">`Subtotal` viene aggiunto come argomento di <xref:System.Activities.ArgumentDirection.In> in quanto i dati di `Subtotal` fluiscono nell'attività <xref:System.Activities.Statements.Interop>; `DiscountPercent` e `Total` vengono aggiunti come argomenti di <xref:System.Activities.ArgumentDirection.Out> in quanto i relativi dati escono dall'attività <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="b2f10-180">`Subtotal` is added as an <xref:System.Activities.ArgumentDirection.In> argument because the `Subtotal` data flows into the <xref:System.Activities.Statements.Interop> activity, and `DiscountPercent` and `Total` are added as <xref:System.Activities.ArgumentDirection.Out> arguments because their data flows out of the <xref:System.Activities.Statements.Interop> activity.</span></span> <span data-ttu-id="b2f10-181">Si noti che i due argomenti <xref:System.Activities.ArgumentDirection.Out> vengono aggiunti con i nomi `DiscountPercentOut` e `TotalOut` per indicare che rappresentano gli argomenti <xref:System.Activities.ArgumentDirection.Out>.</span><span class="sxs-lookup"><span data-stu-id="b2f10-181">Note that the two <xref:System.Activities.ArgumentDirection.Out> arguments are added with the names `DiscountPercentOut` and `TotalOut` to indicate that they represent <xref:System.Activities.ArgumentDirection.Out> arguments.</span></span> <span data-ttu-id="b2f10-182">Il tipo `DiscountCalculator` viene specificato come proprietà <xref:System.Activities.Statements.Interop> dell'attività <xref:System.Activities.Statements.Interop.ActivityType%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2f10-182">The `DiscountCalculator` type is specified as the <xref:System.Activities.Statements.Interop> activity’s <xref:System.Activities.Statements.Interop.ActivityType%2A>.</span></span>  
  
5.  <span data-ttu-id="b2f10-183">Premere CTRL+F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b2f10-183">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="b2f10-184">Sostituire i diversi valori per il valore `Subtotal` al fine di testare i numerosi livelli di sconto forniti dall'attività `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="b2f10-184">Substitute different values for the `Subtotal` value to test out the different discount levels provided by the `DiscountCalculator` activity.</span></span>  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a><span data-ttu-id="b2f10-185">Utilizzo dell'attività di interoperabilità nell'utilità di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="b2f10-185">Using the Interop Activity in the Workflow Designer</span></span>  
 <span data-ttu-id="b2f10-186">In questo esempio viene creato un flusso di lavoro tramite l'utilità di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b2f10-186">In this example, a workflow is created using the workflow designer.</span></span> <span data-ttu-id="b2f10-187">Questo flusso di lavoro dispone della stessa funzionalità descritta nell'esempio precedente, tuttavia anziché usare un'attività <xref:System.Activities.Statements.WriteLine> per visualizzare lo sconto, l'applicazione host recupera e visualizza le informazioni sullo sconto quando il flusso di lavoro viene completato.</span><span class="sxs-lookup"><span data-stu-id="b2f10-187">This workflow has the same functionality as the previous example, except than instead of using a <xref:System.Activities.Statements.WriteLine> activity to display the discount, the host application retrieves and displays the discount information when the workflow completes.</span></span> <span data-ttu-id="b2f10-188">Inoltre, invece di usare le variabili del flusso di lavoro locale per contenere i dati, gli argomenti vengono creati nell'utilità di progettazione del flusso di lavoro e i valori vengono passati dall'host quando il flusso di lavoro viene richiamato.</span><span class="sxs-lookup"><span data-stu-id="b2f10-188">Also, instead of using local workflow variables to contain the data, arguments are created in the workflow designer and the values are passed in from the host when the workflow is invoked.</span></span>  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a><span data-ttu-id="b2f10-189">Per ospitare PolicyActivity usando un flusso di lavoro creato tramite la relativa utilità di progettazione</span><span class="sxs-lookup"><span data-stu-id="b2f10-189">To host the PolicyActivity using a Workflow Designer-created workflow</span></span>  
  
1.  <span data-ttu-id="b2f10-190">Fare doppio clic su **Workflow1** in **Esplora** e selezionare **eliminare**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-190">Right-click **Workflow1.xaml** in **Solution Explorer** and select **Delete**.</span></span> <span data-ttu-id="b2f10-191">Per confermare scegliere **OK** .</span><span class="sxs-lookup"><span data-stu-id="b2f10-191">Click **OK** to confirm.</span></span>  
  
2.  <span data-ttu-id="b2f10-192">Fare doppio clic su **PolicyInteropHost** in **Esplora** e selezionare **Aggiungi**, **nuovo elemento...** .</span><span class="sxs-lookup"><span data-stu-id="b2f10-192">Right-click **PolicyInteropHost** in **Solution Explorer** and select **Add**, **New Item…**.</span></span>  
  
3.  <span data-ttu-id="b2f10-193">Espandere il **elementi di Visual c#** nodo e selezionare **flusso di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-193">Expand the **Visual C# Items** node and select **Workflow**.</span></span> <span data-ttu-id="b2f10-194">Selezionare **attività** dal **elementi di Visual c#** elenco.</span><span class="sxs-lookup"><span data-stu-id="b2f10-194">Select **Activity** from the **Visual C# Items** list.</span></span>  
  
4.  <span data-ttu-id="b2f10-195">Tipo `DiscountWorkflow` nel **nome** casella e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-195">Type `DiscountWorkflow` into the **Name** box and click **Add**.</span></span>  
  
5.  <span data-ttu-id="b2f10-196">Fare clic su di **argomenti** pulsante sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per visualizzare il **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="b2f10-196">Click the **Arguments** button on the lower left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
6.  <span data-ttu-id="b2f10-197">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-197">Click **Create Argument**.</span></span>  
  
7.  <span data-ttu-id="b2f10-198">Tipo `Subtotal` nel **nome** , quindi selezionare **In** dal **direzione** elenco a discesa, selezionare **doppie** dal **Tipo di argomento** elenco a discesa, quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="b2f10-198">Type `Subtotal` into the **Name** box, select **In** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2f10-199">Se **doppie** non si trova nel **tipo di argomento** elenco a discesa, seleziona **Cerca tipi...** , tipo `System.Double` nel **nome del tipo** casella e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-199">If **Double** is not in the **Argument type** drop-down list, select **Browse for Types …**, type `System.Double` in the **Type Name** box, and click **OK**.</span></span>  
  
8.  <span data-ttu-id="b2f10-200">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-200">Click **Create Argument**.</span></span>  
  
9. <span data-ttu-id="b2f10-201">Tipo `DiscountPercent` nel **nome** , quindi selezionare **Out** dal **direzione** elenco a discesa, selezionare **doppie** dal **Tipo di argomento** elenco a discesa, quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="b2f10-201">Type `DiscountPercent` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
10. <span data-ttu-id="b2f10-202">Fare clic su **Crea argomento**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-202">Click **Create Argument**.</span></span>  
  
11. <span data-ttu-id="b2f10-203">Tipo `Total` nel **nome** , quindi selezionare **Out** dal **direzione** elenco a discesa, selezionare **doppie** dal **Tipo di argomento** elenco a discesa, quindi premere INVIO per salvare l'argomento.</span><span class="sxs-lookup"><span data-stu-id="b2f10-203">Type `Total` into the **Name** box, select **Out** from the **Direction** drop-down, select **Double** from the **Argument type** drop-down, and then press ENTER to save the argument.</span></span>  
  
12. <span data-ttu-id="b2f10-204">Fare clic su di **argomenti** pulsante sul lato inferiore sinistro della finestra di progettazione del flusso di lavoro per chiudere la **argomenti** riquadro.</span><span class="sxs-lookup"><span data-stu-id="b2f10-204">Click the **Arguments** button on the lower left side of the workflow designer to close the **Arguments** pane.</span></span>  
  
13. <span data-ttu-id="b2f10-205">Trascinare un **sequenza** attività dal **flusso di controllo** sezione il **della casella degli strumenti** e rilasciarlo nell'area di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b2f10-205">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the workflow designer surface.</span></span>  
  
14. <span data-ttu-id="b2f10-206">Trascinare un **interoperabilità** attività dal **migrazione** sezione il **della casella degli strumenti** e rilasciarlo nel **sequenza** attività.</span><span class="sxs-lookup"><span data-stu-id="b2f10-206">Drag an **Interop** activity from the **Migration** section of the **Toolbox** and drop it in the **Sequence** activity.</span></span>  
  
15. <span data-ttu-id="b2f10-207">Fare clic sul **interoperabilità** attività di **fare clic per cercare...**</span><span class="sxs-lookup"><span data-stu-id="b2f10-207">Click the **Interop** activity on the **Click to browse…**</span></span> <span data-ttu-id="b2f10-208">etichetta, digitare **DiscountCalculator** nel **nome del tipo** casella e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-208">label, type **DiscountCalculator** in the **Type Name** box, and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2f10-209">Quando l'attività <xref:System.Activities.Statements.Interop> viene aggiunta al flusso di lavoro e il tipo `DiscountCalculator` viene specificato come la relativa proprietà <xref:System.Activities.Statements.Interop.ActivityType%2A>, l'attività <xref:System.Activities.Statements.Interop> espone tre argomenti <xref:System.Activities.ArgumentDirection.In> e tre argomenti <xref:System.Activities.ArgumentDirection.Out> che rappresentano le tre proprietà pubbliche dell'attività `DiscountCalculator`.</span><span class="sxs-lookup"><span data-stu-id="b2f10-209">When the <xref:System.Activities.Statements.Interop> activity is added to the workflow and the `DiscountCalculator` type is specified as its <xref:System.Activities.Statements.Interop.ActivityType%2A>, the <xref:System.Activities.Statements.Interop> activity exposes three <xref:System.Activities.ArgumentDirection.In> arguments and three <xref:System.Activities.ArgumentDirection.Out> arguments that represent the three public properties of the `DiscountCalculator` activity.</span></span> <span data-ttu-id="b2f10-210">Il <xref:System.Activities.ArgumentDirection.In> argomenti con lo stesso nome delle tre proprietà pubbliche e i tre <xref:System.Activities.ArgumentDirection.Out> argomenti hanno gli stessi nomi con **Out** aggiunto al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b2f10-210">The <xref:System.Activities.ArgumentDirection.In> arguments have the same name as the three public properties, and the three <xref:System.Activities.ArgumentDirection.Out> arguments have the same names with **Out** appended to the property name.</span></span> <span data-ttu-id="b2f10-211">Nei passaggi seguenti gli argomenti del flusso di lavoro creati in precedenza vengono associati agli argomenti dell'attività <xref:System.Activities.Statements.Interop>.</span><span class="sxs-lookup"><span data-stu-id="b2f10-211">In the following steps, the workflow arguments created in the previous steps are bound to the <xref:System.Activities.Statements.Interop> activity’s arguments.</span></span>  
  
16. <span data-ttu-id="b2f10-212">Tipo `DiscountPercent` nel **immettere un'espressione VB** casella a destra del **DiscountPercentOut** proprietà e premere TAB.</span><span class="sxs-lookup"><span data-stu-id="b2f10-212">Type `DiscountPercent` into the **Enter a VB expression** box to the right of the **DiscountPercentOut** property and press TAB.</span></span>  
  
17. <span data-ttu-id="b2f10-213">Tipo `Subtotal` nel **immettere un'espressione VB** casella a destra del **Subtotal** proprietà e premere TAB.</span><span class="sxs-lookup"><span data-stu-id="b2f10-213">Type `Subtotal` into the **Enter a VB expression** box to the right of the **Subtotal** property and press TAB.</span></span>  
  
18. <span data-ttu-id="b2f10-214">Tipo `Total` nel **immettere un'espressione VB** casella a destra del **TotalOut** proprietà e premere TAB.</span><span class="sxs-lookup"><span data-stu-id="b2f10-214">Type `Total` into the **Enter a VB expression** box to the right of the **TotalOut** property and press TAB.</span></span>  
  
19. <span data-ttu-id="b2f10-215">Fare doppio clic su **Program.cs** in **Esplora** e selezionare **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="b2f10-215">Right-click **Program.cs** in **Solution Explorer** and select **View Code**.</span></span>  
  
20. <span data-ttu-id="b2f10-216">Aggiungere la seguente istruzione `using` all'inizio del file.</span><span class="sxs-lookup"><span data-stu-id="b2f10-216">Add the following `using` statement at the top of the file.</span></span>  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
21. <span data-ttu-id="b2f10-217">Impostare come commento la chiamata al metodo `CalculateDiscountInCode` nel metodo `Main` e aggiungere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b2f10-217">Comment out the call to the `CalculateDiscountInCode` method in the `Main` method and add the following code.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b2f10-218">Se non è stata seguita la procedura precedente e il codice `Main` predefinito è presente, sostituire il contenuto di `Main` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b2f10-218">If you did not follow the previous procedure and the default `Main` code is present, replace the contents of `Main` with the following code.</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingDesignerWorkflow();  
        //CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
22. <span data-ttu-id="b2f10-219">Creare un nuovo metodo nella classe `Program` denominato `CalculateDiscountUsingDesignerWorkflow` contenente il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b2f10-219">Create a new method in the `Program` class called `CalculateDiscountUsingDesignerWorkflow` that contains the following code.</span></span>  
  
    ```csharp  
    static void CalculateDiscountUsingDesignerWorkflow()  
    {  
        double SubtotalValue = 125.99;  
        Dictionary<string, object> wfargs = new Dictionary<string, object>  
        {  
            {"Subtotal", SubtotalValue}  
        };  
  
        Activity wf = new DiscountWorkflow();  
  
        IDictionary<string, object> outputs =  
            WorkflowInvoker.Invoke(wf, wfargs);  
  
        Console.WriteLine("Subtotal: {0:C}, Discount {1}%, Total {2:C}",  
            SubtotalValue, (double)outputs["DiscountPercent"] * 100,  
            outputs["Total"]);  
    }  
    ```  
  
23. <span data-ttu-id="b2f10-220">Premere CTRL+F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b2f10-220">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="b2f10-221">Per specificare un importo `Subtotal` diverso, modificare il valore di `SubtotalValue` nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b2f10-221">To specify a different `Subtotal` amount, change the value of `SubtotalValue` in the following code.</span></span>  
  
    ```csharp  
    double SubtotalValue = 125.99; // Change this value.  
    ```  
  
## <a name="rules-features-overview"></a><span data-ttu-id="b2f10-222">Panoramica sulle funzionalità delle regole</span><span class="sxs-lookup"><span data-stu-id="b2f10-222">Rules Features Overview</span></span>  
 <span data-ttu-id="b2f10-223">Il motore di regole in [!INCLUDE[wf1](../../../includes/wf1-md.md)] facilita l'elaborazione di regole basata sulla priorità con supporto del concatenamento diretto.</span><span class="sxs-lookup"><span data-stu-id="b2f10-223">The [!INCLUDE[wf1](../../../includes/wf1-md.md)] rules engine provides support for processing rules in a priority-based manner with support for forward chaining.</span></span> <span data-ttu-id="b2f10-224">Le regole possono essere valutate per un singolo elemento o per gli elementi di una raccolta.</span><span class="sxs-lookup"><span data-stu-id="b2f10-224">Rules can be evaluated for a single item or for items in a collection.</span></span> <span data-ttu-id="b2f10-225">Per una panoramica sulle regole e per informazioni sulla funzionalità di regole specifiche, fare riferimento alla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b2f10-225">For an overview of rules and information on specific rules functionality, please refer to the following table.</span></span>  
  
|<span data-ttu-id="b2f10-226">Funzionalità delle regole</span><span class="sxs-lookup"><span data-stu-id="b2f10-226">Rules Feature</span></span>|<span data-ttu-id="b2f10-227">Documentazione</span><span class="sxs-lookup"><span data-stu-id="b2f10-227">Documentation</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="b2f10-228">Panoramica sulle regole</span><span class="sxs-lookup"><span data-stu-id="b2f10-228">Rules Overview</span></span>|[<span data-ttu-id="b2f10-229">Introduzione al motore regole di Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="b2f10-229">Introduction to the Windows Workflow Foundation Rules Engine</span></span>](http://go.microsoft.com/fwlink/?LinkID=152836)|  
|<span data-ttu-id="b2f10-230">RuleSet</span><span class="sxs-lookup"><span data-stu-id="b2f10-230">RuleSet</span></span>|<span data-ttu-id="b2f10-231">[Uso di RuleSet in flussi di lavoro](http://go.microsoft.com/fwlink/?LinkId=178516) e<xref:System.Workflow.Activities.Rules.RuleSet></span><span class="sxs-lookup"><span data-stu-id="b2f10-231">[Using RuleSets in Workflows](http://go.microsoft.com/fwlink/?LinkId=178516) and <xref:System.Workflow.Activities.Rules.RuleSet></span></span>|  
|<span data-ttu-id="b2f10-232">Valutazione delle regole</span><span class="sxs-lookup"><span data-stu-id="b2f10-232">Evaluation of Rules</span></span>|[<span data-ttu-id="b2f10-233">Valutazione delle regole di RuleSet</span><span class="sxs-lookup"><span data-stu-id="b2f10-233">Rules Evaluation in RuleSets</span></span>](http://go.microsoft.com/fwlink/?LinkId=178517)|  
|<span data-ttu-id="b2f10-234">Concatenamento di regole</span><span class="sxs-lookup"><span data-stu-id="b2f10-234">Rules Chaining</span></span>|<span data-ttu-id="b2f10-235">[Controllo del concatenamento diretto](http://go.microsoft.com/fwlink/?LinkId=178518) e [concatenamento diretto di regole](http://go.microsoft.com/fwlink/?LinkId=178519)</span><span class="sxs-lookup"><span data-stu-id="b2f10-235">[Forward Chaining Control](http://go.microsoft.com/fwlink/?LinkId=178518) and [Forward Chaining of Rules](http://go.microsoft.com/fwlink/?LinkId=178519)</span></span>|  
|<span data-ttu-id="b2f10-236">Elaborazione di raccolte nelle regole</span><span class="sxs-lookup"><span data-stu-id="b2f10-236">Processing Collections in Rules</span></span>|[<span data-ttu-id="b2f10-237">Elaborazione di raccolte nelle regole</span><span class="sxs-lookup"><span data-stu-id="b2f10-237">Processing Collections in Rules</span></span>](http://go.microsoft.com/fwlink/?LinkId=178520)|  
|<span data-ttu-id="b2f10-238">Utilizzo dell'attività PolicyActivity</span><span class="sxs-lookup"><span data-stu-id="b2f10-238">Using the PolicyActivity</span></span>|<span data-ttu-id="b2f10-239">[Utilizzo dell'attività PolicyActivity](http://go.microsoft.com/fwlink/?LinkId=178521) e<xref:System.Workflow.Activities.PolicyActivity></span><span class="sxs-lookup"><span data-stu-id="b2f10-239">[Using the PolicyActivity Activity](http://go.microsoft.com/fwlink/?LinkId=178521) and <xref:System.Workflow.Activities.PolicyActivity></span></span>|  
  
 <span data-ttu-id="b2f10-240">I flussi di lavoro creati in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] non usano tutte le funzionalità delle regole fornite da [!INCLUDE[wf1](../../../includes/wf1-md.md)], ad esempio le condizioni di attività dichiarative e le attività condizionali quali <xref:System.Workflow.Activities.ConditionedActivityGroup> e <xref:System.Workflow.Activities.ReplicatorActivity>.</span><span class="sxs-lookup"><span data-stu-id="b2f10-240">Workflows created in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] do not use all of the rules features provided by [!INCLUDE[wf1](../../../includes/wf1-md.md)], such as declarative activity conditions and conditional activities such as the <xref:System.Workflow.Activities.ConditionedActivityGroup> and <xref:System.Workflow.Activities.ReplicatorActivity>.</span></span> <span data-ttu-id="b2f10-241">Se necessario, questa funzionalità è disponibile per i flussi di lavoro creati tramite [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] e [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2f10-241">If required, this functionality is available for workflows created using [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] and [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)].</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="b2f10-242">[Materiale sussidiario sulla migrazione](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span><span class="sxs-lookup"><span data-stu-id="b2f10-242"> [Migration Guidance](../../../docs/framework/windows-workflow-foundation/migration-guidance.md).</span></span>
