---
title: Sviluppare controlli personalizzati
description: Informazioni sui controlli Windows Form. In particolare, si apprenderà come combinare i controlli esistenti, estendere i controlli esistenti e creare controlli personalizzati.
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], developing using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 236cebc0-bd71-4f18-9fd6-5d0e592375df
ms.openlocfilehash: 12013496c9650489fdd7512206317000fc0ec78c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618376"
---
# <a name="developing-custom-windows-forms-controls-with-the-net-framework"></a><span data-ttu-id="15436-104">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="15436-104">Developing Custom Windows Forms Controls with the .NET Framework</span></span>
<span data-ttu-id="15436-105">I controlli Windows Form sono componenti riutilizzabili che incapsulano funzionalità dell'interfaccia utente e vengono usati nelle applicazioni basate su Windows sul lato client.</span><span class="sxs-lookup"><span data-stu-id="15436-105">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side Windows-based applications.</span></span> <span data-ttu-id="15436-106">Windows Form fornisce numerosi controlli pronti per l'uso, nonché l'infrastruttura per lo sviluppo di controlli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="15436-106">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="15436-107">È possibile combinare ed estendere i controlli esistenti oppure creare controlli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="15436-107">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="15436-108">Questa sezione fornisce informazioni complementari ed esempi per lo sviluppo di controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="15436-108">This section provides background information and samples to help you develop Windows Forms controls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15436-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="15436-109">In This Section</span></span>  
 [<span data-ttu-id="15436-110">Cenni preliminari sull'utilizzo di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="15436-110">Overview of Using Controls in Windows Forms</span></span>](overview-of-using-controls-in-windows-forms.md)  
 <span data-ttu-id="15436-111">Evidenzia gli elementi essenziali dell'uso di controlli nelle applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="15436-111">Highlights the essential elements of using controls in Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="15436-112">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="15436-112">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)  
 <span data-ttu-id="15436-113">Descrive i diversi tipi di controlli personalizzati che è possibile creare con lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="15436-113">Describes the different kinds of custom controls you can author with the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="15436-114">Nozioni fondamentali sullo sviluppo di controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="15436-114">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)  
 <span data-ttu-id="15436-115">Descrive i passaggi iniziali dello sviluppo di un controllo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="15436-115">Discusses the first steps in developing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="15436-116">Proprietà dei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="15436-116">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)  
 <span data-ttu-id="15436-117">Mostra come aggiungere le proprietà ai controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="15436-117">Shows how to add to properties to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="15436-118">Eventi dei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="15436-118">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)  
 <span data-ttu-id="15436-119">Mostra come gestire e definire gli eventi nei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="15436-119">Shows how to handle and define events in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="15436-120">Attributi nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="15436-120">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="15436-121">Descrive gli attributi che è possibile applicare alle proprietà o ad altri membri e componenti dei controlli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="15436-121">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 [<span data-ttu-id="15436-122">Disegno e rendering di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="15436-122">Custom Control Painting and Rendering</span></span>](custom-control-painting-and-rendering.md)  
 <span data-ttu-id="15436-123">Mostra come personalizzare l'aspetto dei controlli.</span><span class="sxs-lookup"><span data-stu-id="15436-123">Shows how to customize the appearance of your controls.</span></span>  
  
 [<span data-ttu-id="15436-124">Layout di controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="15436-124">Layout in Windows Forms Controls</span></span>](layout-in-windows-forms-controls.md)  
 <span data-ttu-id="15436-125">Mostra come creare layout sofisticati per controlli e form.</span><span class="sxs-lookup"><span data-stu-id="15436-125">Shows how to create sophisticated layouts for your controls and forms.</span></span>  
  
 [<span data-ttu-id="15436-126">Multithreading nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="15436-126">Multithreading in Windows Forms Controls</span></span>](multithreading-in-windows-forms-controls.md)  
 <span data-ttu-id="15436-127">Mostra come implementare i controlli con multithreading.</span><span class="sxs-lookup"><span data-stu-id="15436-127">Shows how to implement multithreaded controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="15436-128">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="15436-128">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="15436-129">Descrive la classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="15436-129">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="15436-130">Descrive la classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="15436-130">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="15436-131">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="15436-131">Related Sections</span></span>  
 <span data-ttu-id="15436-132">[Attributi per componenti in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="15436-132">[Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))</span></span>  
 <span data-ttu-id="15436-133">Elenca gli attributi dei metadati da applicare ai componenti e ai controlli in modo che vengano visualizzati correttamente in fase di progettazione nelle finestre di progettazione visiva.</span><span class="sxs-lookup"><span data-stu-id="15436-133">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 <span data-ttu-id="15436-134">[Estensione del supporto in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="15436-134">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>  
 <span data-ttu-id="15436-135">Descrive come implementare classi, quali editor e finestre di progettazione, che forniscono supporto in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="15436-135">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>  
  
 <span data-ttu-id="15436-136">[Procedura: concedere in licenza componenti e controlli](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="15436-136">[How to: License Components and Controls](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fe8b1eh9(v=vs.120))</span></span>  
 <span data-ttu-id="15436-137">Descrive come implementare le licenze nel controllo o nel componente.</span><span class="sxs-lookup"><span data-stu-id="15436-137">Describes how to implement licensing in your control or component.</span></span>  
  
 <span data-ttu-id="15436-138">Vedere anche [Sviluppo di controlli Windows Form in fase di progettazione](developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="15436-138">Also see [Developing Windows Forms Controls at Design Time](developing-windows-forms-controls-at-design-time.md).</span></span>
