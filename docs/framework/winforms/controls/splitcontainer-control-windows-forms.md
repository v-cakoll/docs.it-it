---
title: Controllo SplitContainer
ms.date: 03/30/2017
helpviewer_keywords:
- splitter windows
- SplitContainer control [Windows Forms]
ms.assetid: 2e36f17f-5c39-4fb4-bb09-7ce3ef823402
ms.openlocfilehash: ac04f60847aa6f77c11637f37b5ec94b6f7ef341
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742912"
---
# <a name="splitcontainer-control-windows-forms"></a><span data-ttu-id="1e63e-102">Controllo SplitContainer (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="1e63e-102">SplitContainer Control (Windows Forms)</span></span>
<span data-ttu-id="1e63e-103">Il controllo `SplitContainer` Windows Form può essere considerato un oggetto composto, poiché è costituito da due pannelli separati da una barra mobile.</span><span class="sxs-lookup"><span data-stu-id="1e63e-103">The Windows Forms `SplitContainer` control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="1e63e-104">Quando il puntatore del mouse viene posizionato sopra la barra, assume una forma diversa per indicare che la barra è mobile.</span><span class="sxs-lookup"><span data-stu-id="1e63e-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e63e-105">Nella **casella degli strumenti**, questo controllo sostituisce il controllo <xref:System.Windows.Forms.Splitter> che era presente nella versione precedente di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1e63e-105">In the **Toolbox**, this control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="1e63e-106">È consigliabile usare il controllo `SplitContainer` anziché il controllo <xref:System.Windows.Forms.Splitter>.</span><span class="sxs-lookup"><span data-stu-id="1e63e-106">The `SplitContainer` control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="1e63e-107">La classe <xref:System.Windows.Forms.Splitter> è ancora inclusa in .NET Framework per assicurare la compatibilità con le applicazioni esistenti, ma per i nuovi progetti si consiglia di usare il controllo `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="1e63e-107">The <xref:System.Windows.Forms.Splitter> class is still included in the .NET Framework for compatibility with existing applications, but we strongly encourage you to use the `SplitContainer` control for new projects.</span></span>  
  
 <span data-ttu-id="1e63e-108">Il controllo `SplitContainer` consente di creare complesse interfacce utente, in cui l'elemento selezionato in un pannello determina in genere gli oggetti visualizzati nell'altro.</span><span class="sxs-lookup"><span data-stu-id="1e63e-108">The `SplitContainer` control lets you create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="1e63e-109">Questa disposizione è particolarmente efficace per la visualizzazione e la ricerca di informazioni.</span><span class="sxs-lookup"><span data-stu-id="1e63e-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="1e63e-110">Grazie alla presenza dei due pannelli è possibile aggregare le informazioni in aree, mentre la barra di divisione consente di ridimensionare i pannelli.</span><span class="sxs-lookup"><span data-stu-id="1e63e-110">Having two panels allow you to aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1e63e-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="1e63e-111">In This Section</span></span>  
 [<span data-ttu-id="1e63e-112">Panoramica sul controllo SplitContainer</span><span class="sxs-lookup"><span data-stu-id="1e63e-112">SplitContainer Control Overview</span></span>](splitcontainer-control-overview-windows-forms.md)  
 <span data-ttu-id="1e63e-113">Introduce il controllo `SplitContainer` e descrive le proprietà, i metodi e gli eventi correlati usati più comunemente.</span><span class="sxs-lookup"><span data-stu-id="1e63e-113">Introduces the `SplitContainer` control and describes the commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="1e63e-114">Procedura: Definire il ridimensionamento e il posizionamento in una finestra divisa</span><span class="sxs-lookup"><span data-stu-id="1e63e-114">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 <span data-ttu-id="1e63e-115">Descrive come controllare la barra di divisione nel controllo `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="1e63e-115">Describes how to control the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="1e63e-116">Procedura: Suddividere una finestra orizzontalmente</span><span class="sxs-lookup"><span data-stu-id="1e63e-116">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)  
 <span data-ttu-id="1e63e-117">Descrive come controllare l'orientamento della barra di divisione nel controllo `SplitContainer`.</span><span class="sxs-lookup"><span data-stu-id="1e63e-117">Describes how to control the orientation of the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="1e63e-118">Procedura: Creare un'interfaccia utente a più riquadri con Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e63e-118">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="1e63e-119">Crea un'interfaccia utente a più riquadri simile a quella usata in Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="1e63e-119">Creates a multi-pane user interface that is similar to the one used in Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="1e63e-120">Vedere anche [procedura: suddividere una finestra orizzontalmente usando la](how-to-split-a-window-horizontally-using-the-designer.md)finestra di progettazione, [procedura: creare un'interfaccia di tipo Esplora risorse in un Windows Form](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [procedura: creare un'interfaccia utente a più riquadri con Windows Forms usando la finestra di progettazione](create-a-multipane-user-interface-with-wf-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="1e63e-120">Also see [How to: Split a Window Horizontally Using the Designer](how-to-split-a-window-horizontally-using-the-designer.md), [How to: Create a Windows Explorer–Style Interface on a Windows Form](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [How to: Create a Multipane User Interface with Windows Forms Using the Designer](create-a-multipane-user-interface-with-wf-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1e63e-121">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="1e63e-121">Reference</span></span>  
 <span data-ttu-id="1e63e-122">Classe <xref:System.Windows.Forms.SplitContainer></span><span class="sxs-lookup"><span data-stu-id="1e63e-122"><xref:System.Windows.Forms.SplitContainer> class</span></span>  
 <span data-ttu-id="1e63e-123">Descrive la classe e fornisce i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="1e63e-123">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1e63e-124">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="1e63e-124">Related Sections</span></span>  
 [<span data-ttu-id="1e63e-125">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e63e-125">Windows Forms Controls</span></span>](index.md)  
 <span data-ttu-id="1e63e-126">Fornisce collegamenti ad argomenti relativi ai controlli appositamente progettati per l'uso con Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1e63e-126">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="1e63e-127">Controlli da utilizzare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="1e63e-127">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="1e63e-128">Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.</span><span class="sxs-lookup"><span data-stu-id="1e63e-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
