---
title: Utilizzo di controlli WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e616019d53648058d51a3d0df457b1380aaf3b1
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="using-wpf-controls"></a><span data-ttu-id="f989d-102">Utilizzo di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="f989d-102">Using WPF Controls</span></span>
<span data-ttu-id="f989d-103">È possibile utilizzare i controlli Windows Presentation Foundation (WPF) in applicazioni basate su Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f989d-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="f989d-104">Anche se si tratta di due tecnologie di visualizzazione diversa, si integrano perfettamente.</span><span class="sxs-lookup"><span data-stu-id="f989d-104">Although these are two different view technologies, they interoperate smoothly.</span></span>  
  
 <span data-ttu-id="f989d-105">Progettazione Windows Form fornisce un ambiente di progettazione visiva per l'hosting di controlli Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="f989d-105">The Windows Forms Designer provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="f989d-106">Un controllo WPF è ospitato da un controllo Windows Form speciale denominato <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="f989d-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="f989d-107">Questo controllo consente il controllo WPF a fanno parte del layout del form e di ricevere i messaggi di tastiera e mouse.</span><span class="sxs-lookup"><span data-stu-id="f989d-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="f989d-108">In fase di progettazione, è possibile disporre di <xref:System.Windows.Forms.Integration.ElementHost> controllare esattamente come qualsiasi controllo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f989d-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>  
  
 <span data-ttu-id="f989d-109">È anche possibile utilizzare i controlli Windows Form nelle applicazioni basate su WPF.</span><span class="sxs-lookup"><span data-stu-id="f989d-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="f989d-110">Per ulteriori informazioni, vedere [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26).</span><span class="sxs-lookup"><span data-stu-id="f989d-110">For more information, see [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f989d-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="f989d-111">In This Section</span></span>  
 [<span data-ttu-id="f989d-112">Procedura: Copiare e incollare un controllo ElementHost in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f989d-112">How to: Copy and Paste an ElementHost Control at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 <span data-ttu-id="f989d-113">Viene illustrato come copiare un controllo Windows Presentation Foundation in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f989d-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>  
  
 [<span data-ttu-id="f989d-114">Procedura dettagliata: Disposizione del contenuto WPF in Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f989d-114">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="f989d-115">Viene illustrato come utilizzare le funzionalità di layout di Windows Form, ad esempio l'ancoraggio e le guide di allineamento, per disporre i controlli Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="f989d-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>  
  
 [<span data-ttu-id="f989d-116">Procedura dettagliata: Modifica delle proprietà di un elemento WPF ospitato in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f989d-116">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 <span data-ttu-id="f989d-117">Viene illustrato il flusso di lavoro tra Progettazione Windows Form e [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] per modificare le proprietà sui controlli WPF.</span><span class="sxs-lookup"><span data-stu-id="f989d-117">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] for changing properties on WPF controls.</span></span>  
  
 [<span data-ttu-id="f989d-118">Procedura dettagliata: Creazione di nuovo contenuto WPF in Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f989d-118">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="f989d-119">Viene illustrato come creare un controllo Windows Presentation Foundation per l'utilizzo in applicazioni basate su Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f989d-119">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>  
  
 [<span data-ttu-id="f989d-120">Procedura dettagliata: Copiare e incollare un controllo ElementHost in Windows Form separati</span><span class="sxs-lookup"><span data-stu-id="f989d-120">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 <span data-ttu-id="f989d-121">Viene illustrato come copiare un controllo Windows Presentation Foundation da un Windows Form a un'altra.</span><span class="sxs-lookup"><span data-stu-id="f989d-121">Shows how to copy a Windows Presentation Foundation control from one Windows Form to another.</span></span>  
  
 [<span data-ttu-id="f989d-122">Procedura dettagliata: Assegnazione del contenuto WPF in Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f989d-122">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="f989d-123">Viene illustrato come selezionare i tipi di controllo di Windows Presentation Foundation che si desidera visualizzare nel form.</span><span class="sxs-lookup"><span data-stu-id="f989d-123">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>  
  
 [<span data-ttu-id="f989d-124">Procedura dettagliata: Applicazione di stili al contenuto WPF</span><span class="sxs-lookup"><span data-stu-id="f989d-124">Walkthrough: Styling WPF Content</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 <span data-ttu-id="f989d-125">Viene illustrato il flusso di lavoro tra Progettazione Windows Form e [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] per l'applicazione di stili ai controlli Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="f989d-125">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f989d-126">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="f989d-126">Reference</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <span data-ttu-id="f989d-127">Descrive una classe che è possibile utilizzare per ospitare i controlli Windows Presentation Foundation nelle applicazioni basate su Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f989d-127">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 <span data-ttu-id="f989d-128">Descrive una classe che consente ai controlli host di Windows Form nell'applicazione basata su Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="f989d-128">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f989d-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="f989d-129">Related Sections</span></span>  
 [<span data-ttu-id="f989d-130">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="f989d-130">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 <span data-ttu-id="f989d-131">Viene descritta l'interazione tra le tecnologie di Windows Presentation Foundation e Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f989d-131">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>  
  
 [<span data-ttu-id="f989d-132">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="f989d-132">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 <span data-ttu-id="f989d-133">Viene descritto come progettare i controlli Windows Presentation Foundation in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f989d-133">Describes how to design Windows Presentation Foundation controls in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>
