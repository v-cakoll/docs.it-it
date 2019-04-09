---
title: 'Attività 1: Creare una nuova applicazione Windows Presentation Foundation'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: dae523714862ed36d36e65b51be62acff9b17f51
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193401"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="0c3ce-102">Attività 1: Creare una nuova applicazione Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="0c3ce-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>
<span data-ttu-id="0c3ce-103">In questa attività verranno creare un'applicazione Windows Presentation Foundation (WPF) vuota usando il modello di Visual Studio dell'applicazione WPF e aggiungere i riferimenti appropriati [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] gli assembly del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-103">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
### <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="0c3ce-104">Per creare il progetto applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="0c3ce-104">To create the WPF Application project</span></span>  
  
1.  <span data-ttu-id="0c3ce-105">Aprire Visual Studio e scegliere il **File** dal menu **New**e quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-105">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="0c3ce-106">Nel **nuovo progetto** finestra di dialogo Seleziona **Visual C#**  oppure **Visual Basic** dal **modelli installati** riquadro a sinistra lato della casella.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="0c3ce-107">Se non viene visualizzato il linguaggio di propria scelta, cercarlo in **altri linguaggi**.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>  
  
3.  <span data-ttu-id="0c3ce-108">Selezionare **Windows** nel **modelli installati** riquadro.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-108">Select **Windows** in the **Installed Templates** pane.</span></span>  
  
4.  <span data-ttu-id="0c3ce-109">Verificare che nel riquadro superiore (il valore predefinito) **.NET Framework 4** è stata selezionata nella casella di riepilogo a discesa e quindi selezionare **applicazione WPF**.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="0c3ce-110">Impostare il nome del progetto in cui **HostingApplication** nella parte inferiore della finestra.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>  
  
6.  <span data-ttu-id="0c3ce-111">Impostare il nome della soluzione **RehostingTheDesigner**.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-111">Set the solution name to **RehostingTheDesigner**.</span></span>  
  
7.  <span data-ttu-id="0c3ce-112">Fare clic su **OK** per creare il progetto di applicazione.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-112">Click **OK** to create the application project.</span></span> <span data-ttu-id="0c3ce-113">Visual Studio crea una UI WPF di base per l'applicazione e include i file di code-behind e XAML appropriato.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-113">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>  
  
8.  <span data-ttu-id="0c3ce-114">Aggiungere riferimenti agli **WorkflowModel** assembly.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="0c3ce-115">A questo scopo, nella **Esplora soluzioni**, fare doppio clic il **HostingApplication** del progetto e selezionare **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>  
  
9. <span data-ttu-id="0c3ce-116">Nel **Aggiungi riferimento** finestra di dialogo, fare clic sulla **.NET** scheda, tenere premuto il tasto CTRL, selezionare gli assembly seguenti e quindi fare clic su **OK**:</span><span class="sxs-lookup"><span data-stu-id="0c3ce-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>  
  
    -   <span data-ttu-id="0c3ce-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="0c3ce-117">System.Activities</span></span>  
  
    -   <span data-ttu-id="0c3ce-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="0c3ce-118">System.Activities.Presentation</span></span>  
  
    -   <span data-ttu-id="0c3ce-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="0c3ce-119">System.Activities.Core.Presentation</span></span>  
  
10. <span data-ttu-id="0c3ce-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-120">Click **OK**.</span></span>  
  
11. <span data-ttu-id="0c3ce-121">Vedere [attività 2: Ospitare la finestra di progettazione del flusso di lavoro](task-2-host-the-workflow-designer.md) per informazioni su come ospitare il canvas di progettazione di progettazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0c3ce-121">See [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c3ce-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c3ce-122">See also</span></span>

- [<span data-ttu-id="0c3ce-123">Riallocazione dell'utilità di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="0c3ce-123">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="0c3ce-124">Attività 2: Ospitare Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="0c3ce-124">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)
