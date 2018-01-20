---
title: 'Procedura: creare un''interfaccia di tipo Esplora risorse in un Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26a91052586843f87c04adf1a31025991d9973db
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="c7e18-102">Procedura: creare un'interfaccia di tipo Esplora risorse in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="c7e18-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="c7e18-103">In Esplora risorse è una scelta dell'interfaccia utente comune per le applicazioni a causa la conoscenza pronta.</span><span class="sxs-lookup"><span data-stu-id="c7e18-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>  
  
 <span data-ttu-id="c7e18-104">In Esplora risorse, in pratica, è un <xref:System.Windows.Forms.TreeView> controllo e un <xref:System.Windows.Forms.ListView> controllo in due pannelli separati.</span><span class="sxs-lookup"><span data-stu-id="c7e18-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="c7e18-105">Il ridimensionabili da una barra di divisione.</span><span class="sxs-lookup"><span data-stu-id="c7e18-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="c7e18-106">Questa disposizione dei controlli è particolarmente efficace per la visualizzazione e la ricerca di informazioni.</span><span class="sxs-lookup"><span data-stu-id="c7e18-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>  
  
 <span data-ttu-id="c7e18-107">La procedura seguente viene illustrato come disporre i controlli in un formato simile a Esplora risorse di Windows.</span><span class="sxs-lookup"><span data-stu-id="c7e18-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="c7e18-108">Essi non viene illustrato come aggiungere le funzionalità di esplorazione file dell'applicazione in Esplora risorse.</span><span class="sxs-lookup"><span data-stu-id="c7e18-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7e18-109">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="c7e18-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c7e18-110">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="c7e18-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c7e18-111">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="c7e18-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="c7e18-112">Per creare un modulo di Windows di tipo Esplora risorse di Windows</span><span class="sxs-lookup"><span data-stu-id="c7e18-112">To create a Windows Explorer-style Windows Form</span></span>  
  
1.  <span data-ttu-id="c7e18-113">Creare un nuovo progetto applicazione Windows.</span><span class="sxs-lookup"><span data-stu-id="c7e18-113">Create a new Windows Application project.</span></span> <span data-ttu-id="c7e18-114">Per informazioni dettagliate, vedere [Procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="c7e18-114">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="c7e18-115">Dal **della casella degli strumenti**:</span><span class="sxs-lookup"><span data-stu-id="c7e18-115">From the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="c7e18-116">Trascinare un <xref:System.Windows.Forms.SplitContainer> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="c7e18-116">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>  
  
    2.  <span data-ttu-id="c7e18-117">Trascinare un <xref:System.Windows.Forms.TreeView> controllare in **SplitterPanel1** (il pannello del <xref:System.Windows.Forms.SplitContainer> controllo contrassegnato **Panel1**).</span><span class="sxs-lookup"><span data-stu-id="c7e18-117">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>  
  
    3.  <span data-ttu-id="c7e18-118">Trascinare un <xref:System.Windows.Forms.ListView> controllare in **pannello SplitterPanel2** (il pannello del <xref:System.Windows.Forms.SplitContainer> controllo contrassegnato **Panel2**).</span><span class="sxs-lookup"><span data-stu-id="c7e18-118">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>  
  
3.  <span data-ttu-id="c7e18-119">Selezionare tutti i tre controlli premendo il tasto CTRL e facendo clic su essi a sua volta.</span><span class="sxs-lookup"><span data-stu-id="c7e18-119">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="c7e18-120">Quando si seleziona il <xref:System.Windows.Forms.SplitContainer> controllo, fare clic sulla barra di divisione, anziché i pannelli.</span><span class="sxs-lookup"><span data-stu-id="c7e18-120">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c7e18-121">Non utilizzare il **Seleziona tutto** comando il **modifica** menu.</span><span class="sxs-lookup"><span data-stu-id="c7e18-121">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="c7e18-122">Se in tal caso, la proprietà necessaria per il passaggio successivo non compariranno nella **proprietà** finestra.</span><span class="sxs-lookup"><span data-stu-id="c7e18-122">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>  
  
4.  <span data-ttu-id="c7e18-123">Nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="c7e18-123">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5.  <span data-ttu-id="c7e18-124">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c7e18-124">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="c7e18-125">Il modulo Visualizza un'interfaccia utente di due parti, simile a quella di Esplora risorse di Windows.</span><span class="sxs-lookup"><span data-stu-id="c7e18-125">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c7e18-126">Quando si trascina la barra di divisione, i pannelli vengono ridimensionati.</span><span class="sxs-lookup"><span data-stu-id="c7e18-126">When you drag the splitter, the panels resize themselves.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e18-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7e18-127">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="c7e18-128">Procedura: Creare un'interfaccia utente a più riquadri con Windows Form</span><span class="sxs-lookup"><span data-stu-id="c7e18-128">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 [<span data-ttu-id="c7e18-129">Procedura: Definire il ridimensionamento e il posizionamento in una finestra divisa</span><span class="sxs-lookup"><span data-stu-id="c7e18-129">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 [<span data-ttu-id="c7e18-130">Procedura: Suddividere una finestra orizzontalmente</span><span class="sxs-lookup"><span data-stu-id="c7e18-130">How to: Split a Window Horizontally</span></span>](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 [<span data-ttu-id="c7e18-131">Controllo SplitContainer</span><span class="sxs-lookup"><span data-stu-id="c7e18-131">SplitContainer Control</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
