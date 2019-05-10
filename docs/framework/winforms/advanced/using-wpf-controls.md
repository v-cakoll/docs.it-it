---
title: Utilizzo di controlli WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 149a2da1303e6b801a439494254a416a38b145a7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211317"
---
# <a name="use-wpf-controls"></a><span data-ttu-id="046da-102">Usare i controlli WPF</span><span class="sxs-lookup"><span data-stu-id="046da-102">Use WPF controls</span></span>

<span data-ttu-id="046da-103">È possibile usare i controlli Windows Presentation Foundation (WPF) nelle applicazioni basate su Windows Form.</span><span class="sxs-lookup"><span data-stu-id="046da-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="046da-104">Anche se questi sono due tecnologie di visualizzazione diversa, si integrano perfettamente.</span><span class="sxs-lookup"><span data-stu-id="046da-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="046da-105">Progettazione Windows Form in Visual Studio offre un ambiente di progettazione visiva per l'hosting di controlli Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="046da-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="046da-106">Un controllo WPF è ospitato da un controllo Windows Form speciale denominato <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="046da-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="046da-107">Questo controllo consente il controllo WPF a partecipare al layout del form e di ricevere i messaggi della tastiera e mouse.</span><span class="sxs-lookup"><span data-stu-id="046da-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="046da-108">In fase di progettazione, è possibile disporre di <xref:System.Windows.Forms.Integration.ElementHost> controllare esattamente come si farebbe qualsiasi controllo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="046da-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="046da-109">È anche possibile usare i controlli Windows Form nelle applicazioni basate su WPF.</span><span class="sxs-lookup"><span data-stu-id="046da-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="046da-110">Per altre informazioni, vedere [progettazione XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="046da-110">For more information, see [Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="046da-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="046da-111">In This Section</span></span>

<span data-ttu-id="046da-112">[Procedura: Copiare e incollare un controllo ElementHost in fase di progettazione](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="046da-112">[How to: Copy and Paste an ElementHost Control at Design Time](how-to-copy-and-paste-an-elementhost-control-at-design-time.md)\\</span></span>
<span data-ttu-id="046da-113">Illustra come copiare un controllo Windows Presentation Foundation in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="046da-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>

<span data-ttu-id="046da-114">[Procedura dettagliata: Disposizione del contenuto WPF in Windows Form in fase di progettazione](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="046da-114">[Walkthrough: Arranging WPF Content on Windows Forms at Design Time](walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="046da-115">Viene illustrato come usare le funzionalità di layout di Windows Form, ad esempio l'ancoraggio e le guide di allineamento, per disporre i controlli Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="046da-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>

<span data-ttu-id="046da-116">[Procedura dettagliata: Creare nuovo contenuto WPF in Windows Form in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="046da-116">[Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="046da-117">Viene illustrato come creare un controllo Windows Presentation Foundation per l'uso nelle applicazioni basate su Windows Form.</span><span class="sxs-lookup"><span data-stu-id="046da-117">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>

<span data-ttu-id="046da-118">[Procedura dettagliata: Assegnazione del contenuto WPF in Windows Form in fase di progettazione](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)\\</span><span class="sxs-lookup"><span data-stu-id="046da-118">[Walkthrough: Assigning WPF Content on Windows Forms at Design Time](walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)\\</span></span>
<span data-ttu-id="046da-119">Viene illustrato come selezionare i tipi di controllo di Windows Presentation Foundation che si desidera visualizzare nel form.</span><span class="sxs-lookup"><span data-stu-id="046da-119">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>

<span data-ttu-id="046da-120">[Procedura dettagliata: Applicazione degli stili WPF contenuto](walkthrough-styling-wpf-content.md)\\</span><span class="sxs-lookup"><span data-stu-id="046da-120">[Walkthrough: Styling WPF Content](walkthrough-styling-wpf-content.md)\\</span></span>
<span data-ttu-id="046da-121">Viene illustrato il flusso di lavoro tra la finestra di progettazione Windows Form e [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] per l'applicazione di stili ai controlli Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="046da-121">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>

## <a name="reference"></a><span data-ttu-id="046da-122">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="046da-122">Reference</span></span>

<xref:System.Windows.Forms.Integration.ElementHost>\
<span data-ttu-id="046da-123">Descrive una classe che è possibile usare per ospitare i controlli Windows Presentation Foundation nelle applicazioni basate su Windows Form.</span><span class="sxs-lookup"><span data-stu-id="046da-123">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>

<xref:System.Windows.Forms.Integration.WindowsFormsHost>\
<span data-ttu-id="046da-124">Descrive una classe che è possibile usare per ospitare i controlli Windows Form nell'applicazione basata su Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="046da-124">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>

## <a name="related-sections"></a><span data-ttu-id="046da-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="046da-125">Related sections</span></span>

<span data-ttu-id="046da-126">[Migrazione e interoperabilità](../../wpf/advanced/migration-and-interoperability.md)\\</span><span class="sxs-lookup"><span data-stu-id="046da-126">[Migration and Interoperability](../../wpf/advanced/migration-and-interoperability.md)\\</span></span>
<span data-ttu-id="046da-127">Viene descritta l'interazione tra le tecnologie di Windows Presentation Foundation e Windows Form.</span><span class="sxs-lookup"><span data-stu-id="046da-127">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>

<span data-ttu-id="046da-128">[Progettazione XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)\\</span><span class="sxs-lookup"><span data-stu-id="046da-128">[Design XAML in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)\\</span></span>
<span data-ttu-id="046da-129">Descrive come progettare i controlli Windows Presentation Foundation in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="046da-129">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
