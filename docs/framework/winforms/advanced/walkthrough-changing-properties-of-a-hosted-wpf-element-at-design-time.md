---
title: "Procedura dettagliata: modifica delle proprietà di un elemento WPF ospitato in fase di progettazione"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46b80ee0c74da7371ac8f7a16d3430b5b753059d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a><span data-ttu-id="ccd7e-102">Procedura dettagliata: modifica delle proprietà di un elemento WPF ospitato in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="ccd7e-102">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>
<span data-ttu-id="ccd7e-103">Questa procedura dettagliata mostra come cambiare i valori delle proprietà di un controllo Windows Presentation Foundation (WPF) incluso in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-103">This walkthrough shows you how to change property values of a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>  
  
 <span data-ttu-id="ccd7e-104">Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ccd7e-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="ccd7e-105">Creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-105">Create the project.</span></span>  
  
-   <span data-ttu-id="ccd7e-106">Creare il controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-106">Create the WPF control.</span></span>  
  
-   <span data-ttu-id="ccd7e-107">Inserire i controlli WPF in Windows Form</span><span class="sxs-lookup"><span data-stu-id="ccd7e-107">Host the WPF controls on a Windows Form.</span></span>  
  
-   <span data-ttu-id="ccd7e-108">Usare WPF Designer per Visual Studio per cambiare i valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-108">Use the WPF Designer for Visual Studio to change property values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ccd7e-109">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ccd7e-110">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="ccd7e-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ccd7e-111">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="ccd7e-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ccd7e-112">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ccd7e-112">Prerequisites</span></span>  
 <span data-ttu-id="ccd7e-113">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ccd7e-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="ccd7e-114">.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="ccd7e-115">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="ccd7e-115">Creating the Project</span></span>  
 <span data-ttu-id="ccd7e-116">Il primo passaggio consiste nella creazione del progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ccd7e-117">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="ccd7e-118">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="ccd7e-118">To create the project</span></span>  
  
-   <span data-ttu-id="ccd7e-119">Creare un nuovo progetto applicazione Windows Forms in Visual Basic o Visual c# denominato `WpfHost`.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `WpfHost`.</span></span>  
  
## <a name="creating-the-wpf-control"></a><span data-ttu-id="ccd7e-120">Creazione del controllo WPF</span><span class="sxs-lookup"><span data-stu-id="ccd7e-120">Creating the WPF Control</span></span>  
 <span data-ttu-id="ccd7e-121">Dopo avere aggiunto un controllo WPF al progetto, è possibile disporlo sul form.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-121">After you add a WPF control to the project, you can arrange it on the form.</span></span>  
  
#### <a name="to-create-wpf-controls"></a><span data-ttu-id="ccd7e-122">Per creare controlli WPF</span><span class="sxs-lookup"><span data-stu-id="ccd7e-122">To create WPF controls</span></span>  
  
1.  <span data-ttu-id="ccd7e-123">Aggiungere un nuovo <xref:System.Windows.Controls.UserControl> WPF al progetto.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-123">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="ccd7e-124">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="ccd7e-125">Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="ccd7e-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="ccd7e-126">Nel **proprietà** finestra, impostare il valore della <xref:System.Windows.Controls.Control.Background%2A> proprietà `Blue`.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-126">In the **Properties** window, set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
3.  <span data-ttu-id="ccd7e-127">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-127">Build the project.</span></span>  
  
## <a name="changing-property-values-on-the-wpf-control"></a><span data-ttu-id="ccd7e-128">Modifica dei valori delle proprietà nel controllo WPF</span><span class="sxs-lookup"><span data-stu-id="ccd7e-128">Changing Property Values on the WPF Control</span></span>  
 <span data-ttu-id="ccd7e-129">Lo smart tag <xref:System.Windows.Forms.Integration.ElementHost> facilita la modifica delle proprietà del contenuto WPF ospitato usando WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-129">The <xref:System.Windows.Forms.Integration.ElementHost> smart tag makes it easy to change properties of hosted WPF content by using the WPF Designer.</span></span>  
  
#### <a name="to-host-a-wpf-control"></a><span data-ttu-id="ccd7e-130">Per includere un controllo WPF</span><span class="sxs-lookup"><span data-stu-id="ccd7e-130">To host a WPF control</span></span>  
  
1.  <span data-ttu-id="ccd7e-131">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-131">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="ccd7e-132">Nel **della casella degli strumenti**nella **controlli utente WPF** scheda, fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nel form.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-132">In the **Toolbox**, in the **WPF User Controls** tab, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="ccd7e-133">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-133">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="ccd7e-134">Nel **ElementHost Tasks** pannello smart tag, seleziona **modifica contenuto ospitato**.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-134">In the **ElementHost Tasks** smart tag panel, select **Edit Hosted Content**.</span></span>  
  
     <span data-ttu-id="ccd7e-135">UserControl1.xaml viene aperto in WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-135">UserControl1.xaml opens in the WPF Designer.</span></span>  
  
4.  <span data-ttu-id="ccd7e-136">Nel **proprietà** finestra, impostare il valore della <xref:System.Windows.Controls.Control.Background%2A> proprietà `Red`.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-136">In the **Properties** window, set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Red`.</span></span>  
  
5.  <span data-ttu-id="ccd7e-137">Ricompilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-137">Rebuild the project.</span></span>  
  
6.  <span data-ttu-id="ccd7e-138">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-138">Open `Form1` in the Windows Forms Designer.</span></span>  
  
     <span data-ttu-id="ccd7e-139">L'istanza di `UserControl1` presenta uno sfondo rosso.</span><span class="sxs-lookup"><span data-stu-id="ccd7e-139">The instance of `UserControl1` has a red background.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd7e-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccd7e-140">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="ccd7e-141">Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ccd7e-141">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="ccd7e-142">Procedura: Allineare un controllo ai bordi dei form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="ccd7e-142">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [<span data-ttu-id="ccd7e-143">Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="ccd7e-143">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="ccd7e-144">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="ccd7e-144">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="ccd7e-145">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="ccd7e-145">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="ccd7e-146">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="ccd7e-146">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
