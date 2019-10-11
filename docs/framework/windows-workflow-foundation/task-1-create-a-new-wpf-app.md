---
title: 'Attività 1: Creare una nuova applicazione Windows Presentation Foundation'
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 3205840da575041b449eb841fc8084e89937fca7
ms.sourcegitcommit: 10db6551ea3c971470cf5d2cc21ba1cbcefe5c55
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2019
ms.locfileid: "72031891"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="565c1-102">Attività 1: Creare una nuova applicazione Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="565c1-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>

<span data-ttu-id="565c1-103">In questa attività verrà creata un'applicazione Windows Presentation Foundation (WPF) vuota utilizzando il modello di Visual Studio dell'applicazione WPF e verranno aggiunti riferimenti agli assembly del flusso di lavoro [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] appropriati.</span><span class="sxs-lookup"><span data-stu-id="565c1-103">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
## <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="565c1-104">Per creare il progetto applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="565c1-104">To create the WPF Application project</span></span>

1. <span data-ttu-id="565c1-105">Aprire Visual Studio e scegliere **nuovo**dal menu **file** , quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="565c1-105">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="565c1-106">Nella finestra di dialogo **nuovo progetto** selezionare **Visual C#**  o **Visual Basic** dal riquadro **modelli installati** sul lato sinistro della casella.</span><span class="sxs-lookup"><span data-stu-id="565c1-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="565c1-107">Se il linguaggio scelto non viene visualizzato, cercare in **altre lingue**.</span><span class="sxs-lookup"><span data-stu-id="565c1-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>

3. <span data-ttu-id="565c1-108">Selezionare **Windows** nel riquadro **modelli installati** .</span><span class="sxs-lookup"><span data-stu-id="565c1-108">Select **Windows** in the **Installed Templates** pane.</span></span>

4. <span data-ttu-id="565c1-109">Nel riquadro superiore, verificare che sia selezionato il valore predefinito **.NET Framework 4** nell'elenco a discesa, quindi selezionare **applicazione WPF**.</span><span class="sxs-lookup"><span data-stu-id="565c1-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>

5. <span data-ttu-id="565c1-110">Impostare il nome del progetto su **HostingApplication** nella parte inferiore della finestra.</span><span class="sxs-lookup"><span data-stu-id="565c1-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>

6. <span data-ttu-id="565c1-111">Impostare il nome della soluzione su **RehostingTheDesigner**.</span><span class="sxs-lookup"><span data-stu-id="565c1-111">Set the solution name to **RehostingTheDesigner**.</span></span>

7. <span data-ttu-id="565c1-112">Fare clic su **OK** per creare il progetto di applicazione.</span><span class="sxs-lookup"><span data-stu-id="565c1-112">Click **OK** to create the application project.</span></span> <span data-ttu-id="565c1-113">Visual Studio crea un'interfaccia utente WPF di base per l'applicazione e include i file XAML e code-behind appropriati.</span><span class="sxs-lookup"><span data-stu-id="565c1-113">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>

8. <span data-ttu-id="565c1-114">Aggiungere riferimenti agli assembly **WorkflowModel** .</span><span class="sxs-lookup"><span data-stu-id="565c1-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="565c1-115">A tale scopo, in **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto **HostingApplication** e scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="565c1-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>

9. <span data-ttu-id="565c1-116">Nella finestra di dialogo **Aggiungi riferimento** fare clic sulla scheda **.NET** , tenere premuto il tasto CTRL, selezionare gli assembly seguenti e quindi fare clic su **OK**:</span><span class="sxs-lookup"><span data-stu-id="565c1-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>

    - <span data-ttu-id="565c1-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="565c1-117">System.Activities</span></span>
    - <span data-ttu-id="565c1-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="565c1-118">System.Activities.Presentation</span></span>
    - <span data-ttu-id="565c1-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="565c1-119">System.Activities.Core.Presentation</span></span>

10. <span data-ttu-id="565c1-120">Vedere [Task 2: Ospitare il Progettazione flussi di lavoro @ no__t-0 per informazioni su come ospitare l'area di progettazione di progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="565c1-120">See [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>

## <a name="see-also"></a><span data-ttu-id="565c1-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="565c1-121">See also</span></span>

- [<span data-ttu-id="565c1-122">Riallocazione di Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="565c1-122">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- <span data-ttu-id="565c1-123">[Task 2: Ospitare il Progettazione flussi di lavoro @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="565c1-123">[Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md)</span></span>
