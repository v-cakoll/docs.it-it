---
title: 'Procedura: Creare un modello di attività personalizzato'
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: b455f8a763859d31405380e25cd7516856e8da2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517849"
---
# <a name="how-to-create-a-custom-activity-template"></a><span data-ttu-id="2931c-102">Procedura: Creare un modello di attività personalizzato</span><span class="sxs-lookup"><span data-stu-id="2931c-102">How to: Create a Custom Activity Template</span></span>
<span data-ttu-id="2931c-103">I modelli di attività personalizzati vengono usati per personalizzare la configurazione delle attività, incluse CompositeActivity personalizzate, in modo che gli utenti non debbano creare individualmente ciascuna attività e configurare manualmente le relative proprietà e altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="2931c-103">Custom activity templates are used to customize the configuration of activities, including custom composite activities, so that users do not have to create each activity individually and configure their properties and other settings manually.</span></span> <span data-ttu-id="2931c-104">Questi modelli personalizzati possono essere resi disponibili nel **della casella degli strumenti** sul [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] o da una finestra di progettazione ospitata nuovamente, da cui gli utenti possono trascinarli nell'area di progettazione preconfigurata.</span><span class="sxs-lookup"><span data-stu-id="2931c-104">These custom templates can be made available in the **Toolbox** on the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] or from a rehosted designer, from which users can drag them onto the preconfigured design surface.</span></span> [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]<span data-ttu-id="2931c-105"> viene fornito con ottimi esempi di tali modelli: il [Progettazione modelli SendAndReceiveReply](/visualstudio/workflow-designer/sendandreceivereply-template-designer) e il [progettazione del modello ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer) nel [messaggistica gli ActivityDesigner](/visualstudio/workflow-designer/messaging-activity-designers) categoria.</span><span class="sxs-lookup"><span data-stu-id="2931c-105"> ships with good examples of such templates: the [SendAndReceiveReply Template Designer](/visualstudio/workflow-designer/sendandreceivereply-template-designer) and the [ReceiveAndSendReply Template Designer](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in the [Messaging Activity Designers](/visualstudio/workflow-designer/messaging-activity-designers) category.</span></span>  
  
 <span data-ttu-id="2931c-106">La prima procedura in questo argomento viene descritto come creare un modello di attività personalizzata per un **ritardo** attività mentre la seconda procedura viene descritto brevemente come renderlo disponibile in un [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] per verificare che il modello personalizzato funzioni.</span><span class="sxs-lookup"><span data-stu-id="2931c-106">The first procedure in this topic describes how to create a custom activity template for a **Delay** activity and the second procedure describes briefly how to make it available in a [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] to verify that the custom template works.</span></span>  
  
 <span data-ttu-id="2931c-107">I modelli di attività personalizzati devono implementare l'oggetto <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span><span class="sxs-lookup"><span data-stu-id="2931c-107">Custom activity templates must implement the <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span></span> <span data-ttu-id="2931c-108">L'interfaccia dispone di un singolo metodo <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> con il quale è possibile creare e configurare le istanze dell'attività usate nel modello.</span><span class="sxs-lookup"><span data-stu-id="2931c-108">The interface has a single <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> method with which you can create and configure the activity instances used in the template.</span></span>  
  
### <a name="to-create-a-template-for-the-delay-activity"></a><span data-ttu-id="2931c-109">Per creare un modello per l'attività Delay</span><span class="sxs-lookup"><span data-stu-id="2931c-109">To create a template for the Delay activity</span></span>  
  
1.  <span data-ttu-id="2931c-110">Avviare [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2931c-110">Start [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="2931c-111">Nel menu **File** scegliere **Nuovo** e quindi selezionare **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="2931c-111">On the **File** menu, point to **New**, and then select **Project**.</span></span>  
  
     <span data-ttu-id="2931c-112">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="2931c-112">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="2931c-113">Nel **tipi di progetto** riquadro, selezionare **flusso di lavoro** da uno di **Visual c#** progetti o **Visual Basic** raggruppamenti in base il preferenze della lingua.</span><span class="sxs-lookup"><span data-stu-id="2931c-113">In the **Project Types** pane, select **Workflow** from either the **Visual C#** projects or **Visual Basic** groupings depending on your language preference.</span></span>  
  
4.  <span data-ttu-id="2931c-114">Nel **modelli** riquadro, selezionare **libreria attività**.</span><span class="sxs-lookup"><span data-stu-id="2931c-114">In the **Templates** pane, select **Activity Library**.</span></span>  
  
5.  <span data-ttu-id="2931c-115">Nel **nome** immettere `DelayActivityTemplate`.</span><span class="sxs-lookup"><span data-stu-id="2931c-115">In the **Name** box, enter `DelayActivityTemplate`.</span></span>  
  
6.  <span data-ttu-id="2931c-116">Accettare le impostazioni predefinite di **percorso** e **Nome soluzione** caselle di testo e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2931c-116">Accept the defaults in the **Location** and **Solution name** text boxes, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="2931c-117">Fare clic sulla directory riferimenti del progetto DelayActivityTemplate in **Esplora** e scegliere **Aggiungi riferimento** per aprire la **Aggiungi riferimento** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="2931c-117">Right-click the References directory of the DelayActivityTemplate project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>  
  
8.  <span data-ttu-id="2931c-118">Passare al **.NET** e selezionare **PresentationFramework** dal **nome componente** colonna a sinistra e fare clic su **OK** per aggiungere un riferimento al file PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="2931c-118">Go to the **.NET** tab and select **PresentationFramework** from the **Component Name** column on the left and click **OK** to add a reference to the PresentationFramework.dll file.</span></span>  
  
9. <span data-ttu-id="2931c-119">Ripetere questa procedura per aggiungere riferimenti ai file System.Activities.Presentation.dll e WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="2931c-119">Repeat this procedure to add references to the System.Activities.Presentation.dll and the WindowsBase.dll files.</span></span>  
  
10. <span data-ttu-id="2931c-120">Fare clic sul progetto DelayActivityTemplate in **Esplora** e scegliere **Aggiungi** e quindi **nuovo elemento** per aprire la **Aggiungi nuovo elemento**la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="2931c-120">Right-click the DelayActivityTemplate project in **Solution Explorer** and choose **Add** and then **New Item** to open the **Add New Item** dialog box.</span></span>  
  
11. <span data-ttu-id="2931c-121">Selezionare il **classe** modello, denominarlo MyDelayTemplate e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2931c-121">Select the **Class** template, name it MyDelayTemplate, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="2931c-122">Aprire il file MyDelayTemplate.cs e aggiungere le istruzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="2931c-122">Open the MyDelayTemplate.cs file and add the following statements.</span></span>  
  
    ```  
    //Namespaces added  
    using System.Activities;  
    using System.Activities.Statements;  
    using System.Activities.Presentation;  
    using System.Windows;  
    ```  
  
13. <span data-ttu-id="2931c-123">Implementare <xref:System.Activities.Presentation.IActivityTemplateFactory> con la classe `MyDelayActivity` con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2931c-123">Implement the <xref:System.Activities.Presentation.IActivityTemplateFactory> with the `MyDelayActivity` class with the following code.</span></span> <span data-ttu-id="2931c-124">In questo modo viene configurata una durata del ritardo di 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="2931c-124">This configures the delay to have a duration of 10 seconds.</span></span>  
  
    ```  
    public sealed class MyDelayActivity : IActivityTemplateFactory  
    {  
        public Activity Create(System.Windows.DependencyObject target)  
        {  
            return new System.Activities.Statements.Delay  
            {  
                DisplayName = "DelayActivityTemplate",  
                Duration = new TimeSpan(0, 0, 10)  
  
            };  
        }  
    }  
    ```  
  
14. <span data-ttu-id="2931c-125">Selezionare **Compila soluzione** dal **compilare** menu per generare il file DelayActivityTemplate.dll.</span><span class="sxs-lookup"><span data-stu-id="2931c-125">Select **Build Solution** from the **Build** menu to generate the DelayActivityTemplate.dll file.</span></span>  
  
### <a name="to-make-the-template-available-in-a-workflow-designer"></a><span data-ttu-id="2931c-126">Per rendere disponibile il modello in Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="2931c-126">To make the template available in a Workflow Designer</span></span>  
  
1.  <span data-ttu-id="2931c-127">Pulsante destro del mouse sulla soluzione DelayActivityTemplate in **Esplora** e scegliere **Aggiungi** e quindi **nuovo progetto** per aprire la **Aggiungi nuovo progetto** la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="2931c-127">Right-click the DelayActivityTemplate solution in **Solution Explorer** and choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="2931c-128">Selezionare il **applicazione Console flusso di lavoro** modello, il nome `CustomActivityTemplateApp`, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2931c-128">Select the **Workflow Console Application** template, name it `CustomActivityTemplateApp`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="2931c-129">Fare clic sulla directory riferimenti del progetto CustomActivityTemplateApp in **Esplora** e scegliere **Aggiungi riferimento** per aprire la **Aggiungi riferimento** finestra di dialogo casella.</span><span class="sxs-lookup"><span data-stu-id="2931c-129">Right-click the References directory of the CustomActivityTemplateApp project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>  
  
4.  <span data-ttu-id="2931c-130">Passare al **progetti** e selezionare **DelayActivityTemplate** dal **nome progetto** colonna a sinistra e fare clic su **OK** per aggiungere un Fare riferimento al file DelayActivityTemplate.dll creato nella prima procedura.</span><span class="sxs-lookup"><span data-stu-id="2931c-130">Go to the **Projects** tab and select **DelayActivityTemplate** from the **Project Name** column on the left and click **OK** to add a reference to the DelayActivityTemplate.dll file that you created in the first procedure.</span></span>  
  
5.  <span data-ttu-id="2931c-131">Pulsante destro del mouse sul progetto CustomActivityTemplateApp in **Esplora** e scegliere **compilare** per compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2931c-131">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Build** to compile the application.</span></span>  
  
6.  <span data-ttu-id="2931c-132">Pulsante destro del mouse sul progetto CustomActivityTemplateApp in **Esplora** e scegliere **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="2931c-132">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Set as Startup Project**.</span></span>  
  
7.  <span data-ttu-id="2931c-133">Selezionare **Avvia senza eseguire debug** dal **Debug** menu e premere un tasto qualsiasi per continuare quando richiesto nella finestra di cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="2931c-133">Select **Start Without Debugging** from the **Debug** menu and press any key to continue when prompted from the cmd.exe window.</span></span>  
  
8.  <span data-ttu-id="2931c-134">Aprire il file Workflow1 XAML e il **della casella degli strumenti**.</span><span class="sxs-lookup"><span data-stu-id="2931c-134">Open the Workflow1.xaml file and open the **Toolbox**.</span></span>  
  
9. <span data-ttu-id="2931c-135">Individuare il **MyDelayActivity** modello il **DelayActivityTemplate** categoria.</span><span class="sxs-lookup"><span data-stu-id="2931c-135">Locate the **MyDelayActivity** template in the **DelayActivityTemplate** category.</span></span> <span data-ttu-id="2931c-136">Trascinarlo nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="2931c-136">Drag it onto the design surface.</span></span> <span data-ttu-id="2931c-137">Confermare il **proprietà** finestra che la `Duration` proprietà è stata impostata su 10 secondi.</span><span class="sxs-lookup"><span data-stu-id="2931c-137">Confirm in the **Properties** window that the `Duration` property has been set to 10 seconds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2931c-138">Esempio</span><span class="sxs-lookup"><span data-stu-id="2931c-138">Example</span></span>  
 <span data-ttu-id="2931c-139">Il file MyDelayActivity.cs deve contenere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2931c-139">The MyDelayActivity.cs file should contain the following code.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
  
//Namespaces added  
using System.Activities;  
using System.Activities.Statements;  
using System.Activities.Presentation;  
using System.Windows;  
  
namespace DelayActivityTemplate  
{  
    public sealed class MyDelayActivity : IActivityTemplateFactory  
    {  
        public Activity Create(System.Windows.DependencyObject target)  
        {  
            return new System.Activities.Statements.Delay  
            {  
                DisplayName = "DelayActivityTemplate",  
                Duration = new TimeSpan(0, 0, 10)  
  
            };  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2931c-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2931c-140">See Also</span></span>  
 <xref:System.Activities.Presentation.IActivityTemplateFactory>  
 [<span data-ttu-id="2931c-141">Personalizzazione della fase di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2931c-141">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
