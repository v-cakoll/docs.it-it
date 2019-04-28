---
title: Utilizzo di controlli WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 24b88e456628c5a0bdc3cded60b0e52a92057851
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747615"
---
# <a name="using-wpf-controls"></a><span data-ttu-id="04656-102">Utilizzo di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="04656-102">Using WPF Controls</span></span>
<span data-ttu-id="04656-103">È possibile usare i controlli Windows Presentation Foundation (WPF) nelle applicazioni basate su Windows Form.</span><span class="sxs-lookup"><span data-stu-id="04656-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="04656-104">Anche se questi sono due tecnologie di visualizzazione diversa, si integrano perfettamente.</span><span class="sxs-lookup"><span data-stu-id="04656-104">Although these are two different view technologies, they interoperate smoothly.</span></span>  
  
 <span data-ttu-id="04656-105">Finestra di progettazione Windows Form fornisce un ambiente di progettazione visiva per l'hosting di controlli Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="04656-105">The Windows Forms Designer provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="04656-106">Un controllo WPF è ospitato da un controllo Windows Form speciale denominato <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="04656-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="04656-107">Questo controllo consente il controllo WPF a partecipare al layout del form e di ricevere i messaggi della tastiera e mouse.</span><span class="sxs-lookup"><span data-stu-id="04656-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="04656-108">In fase di progettazione, è possibile disporre di <xref:System.Windows.Forms.Integration.ElementHost> controllare esattamente come si farebbe qualsiasi controllo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="04656-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>  
  
 <span data-ttu-id="04656-109">È anche possibile usare i controlli Windows Form nelle applicazioni basate su WPF.</span><span class="sxs-lookup"><span data-stu-id="04656-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="04656-110">Per altre informazioni, vedere [progettazione XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="04656-110">For more information, see [Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04656-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="04656-111">In This Section</span></span>  
 [<span data-ttu-id="04656-112">Procedura: Copiare e incollare un controllo ElementHost in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="04656-112">How to: Copy and Paste an ElementHost Control at Design Time</span></span>](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 <span data-ttu-id="04656-113">Illustra come copiare un controllo Windows Presentation Foundation in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="04656-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>  
  
 [<span data-ttu-id="04656-114">Procedura dettagliata: Disposizione del contenuto WPF in Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="04656-114">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="04656-115">Viene illustrato come usare le funzionalità di layout di Windows Form, ad esempio l'ancoraggio e le guide di allineamento, per disporre i controlli Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="04656-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>
  
 [<span data-ttu-id="04656-116">Procedura dettagliata: Creare nuovo contenuto WPF in Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="04656-116">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="04656-117">Viene illustrato come creare un controllo Windows Presentation Foundation per l'uso nelle applicazioni basate su Windows Form.</span><span class="sxs-lookup"><span data-stu-id="04656-117">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>
  
 [<span data-ttu-id="04656-118">Procedura dettagliata: Assegnazione del contenuto WPF in Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="04656-118">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="04656-119">Viene illustrato come selezionare i tipi di controllo di Windows Presentation Foundation che si desidera visualizzare nel form.</span><span class="sxs-lookup"><span data-stu-id="04656-119">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>  
  
 [<span data-ttu-id="04656-120">Procedura dettagliata: Applicazione degli stili WPF contenuto</span><span class="sxs-lookup"><span data-stu-id="04656-120">Walkthrough: Styling WPF Content</span></span>](walkthrough-styling-wpf-content.md)  
 <span data-ttu-id="04656-121">Viene illustrato il flusso di lavoro tra la finestra di progettazione Windows Form e [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] per l'applicazione di stili ai controlli Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="04656-121">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="04656-122">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="04656-122">Reference</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <span data-ttu-id="04656-123">Descrive una classe che è possibile usare per ospitare i controlli Windows Presentation Foundation nelle applicazioni basate su Windows Form.</span><span class="sxs-lookup"><span data-stu-id="04656-123">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 <span data-ttu-id="04656-124">Descrive una classe che è possibile usare per ospitare i controlli Windows Form nell'applicazione basata su Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="04656-124">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="04656-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="04656-125">Related Sections</span></span>  
 [<span data-ttu-id="04656-126">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="04656-126">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)  
 <span data-ttu-id="04656-127">Viene descritta l'interazione tra le tecnologie di Windows Presentation Foundation e Windows Form.</span><span class="sxs-lookup"><span data-stu-id="04656-127">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>  
  
 [<span data-ttu-id="04656-128">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04656-128">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)  
 <span data-ttu-id="04656-129">Descrive come progettare i controlli Windows Presentation Foundation in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="04656-129">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
