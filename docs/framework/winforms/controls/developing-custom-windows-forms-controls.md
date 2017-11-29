---
title: Sviluppo di controlli Windows Form personalizzati con .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], developing using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 236cebc0-bd71-4f18-9fd6-5d0e592375df
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89be7e347556c8ec34296044f17fbfd4450bc127
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="developing-custom-windows-forms-controls-with-the-net-framework"></a><span data-ttu-id="6b164-102">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6b164-102">Developing Custom Windows Forms Controls with the .NET Framework</span></span>
<span data-ttu-id="6b164-103">I controlli Windows Form sono componenti riutilizzabili che incapsulano funzionalità dell'interfaccia utente e vengono usati nelle applicazioni basate su Windows sul lato client.</span><span class="sxs-lookup"><span data-stu-id="6b164-103">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side Windows-based applications.</span></span> <span data-ttu-id="6b164-104">Windows Form fornisce numerosi controlli pronti per l'uso, nonché l'infrastruttura per lo sviluppo di controlli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6b164-104">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="6b164-105">È possibile combinare ed estendere i controlli esistenti oppure creare controlli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6b164-105">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="6b164-106">Questa sezione fornisce informazioni complementari ed esempi per lo sviluppo di controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="6b164-106">This section provides background information and samples to help you develop Windows Forms controls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b164-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6b164-107">In This Section</span></span>  
 [<span data-ttu-id="6b164-108">Cenni preliminari sull'utilizzo di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="6b164-108">Overview of Using Controls in Windows Forms</span></span>](../../../../docs/framework/winforms/controls/overview-of-using-controls-in-windows-forms.md)  
 <span data-ttu-id="6b164-109">Evidenzia gli elementi essenziali dell'uso di controlli nelle applicazioni Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6b164-109">Highlights the essential elements of using controls in Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="6b164-110">Tipi di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="6b164-110">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 <span data-ttu-id="6b164-111">Descrive i diversi tipi di controlli personalizzati che è possibile creare con lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6b164-111">Describes the different kinds of custom controls you can author with the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace.</span></span>  
  
 [<span data-ttu-id="6b164-112">Nozioni fondamentali sullo sviluppo di controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="6b164-112">Windows Forms Control Development Basics</span></span>](../../../../docs/framework/winforms/controls/windows-forms-control-development-basics.md)  
 <span data-ttu-id="6b164-113">Descrive i passaggi iniziali dello sviluppo di un controllo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="6b164-113">Discusses the first steps in developing a Windows Forms control.</span></span>  
  
 [<span data-ttu-id="6b164-114">Proprietà dei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="6b164-114">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 <span data-ttu-id="6b164-115">Mostra come aggiungere le proprietà ai controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="6b164-115">Shows how to add to properties to Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="6b164-116">Eventi nei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="6b164-116">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 <span data-ttu-id="6b164-117">Mostra come gestire e definire gli eventi nei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="6b164-117">Shows how to handle and define events in Windows Forms controls.</span></span>  
  
 [<span data-ttu-id="6b164-118">Attributi nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="6b164-118">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 <span data-ttu-id="6b164-119">Descrive gli attributi che è possibile applicare alle proprietà o ad altri membri e componenti dei controlli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="6b164-119">Describes the attributes you can apply to properties or other members of your custom controls and components.</span></span>  
  
 [<span data-ttu-id="6b164-120">Disegno e rendering di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="6b164-120">Custom Control Painting and Rendering</span></span>](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="6b164-121">Mostra come personalizzare l'aspetto dei controlli.</span><span class="sxs-lookup"><span data-stu-id="6b164-121">Shows how to customize the appearance of your controls.</span></span>  
  
 [<span data-ttu-id="6b164-122">Layout di controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="6b164-122">Layout in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/layout-in-windows-forms-controls.md)  
 <span data-ttu-id="6b164-123">Mostra come creare layout sofisticati per controlli e form.</span><span class="sxs-lookup"><span data-stu-id="6b164-123">Shows how to create sophisticated layouts for your controls and forms.</span></span>  
  
 [<span data-ttu-id="6b164-124">Multithreading nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="6b164-124">Multithreading in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/multithreading-in-windows-forms-controls.md)  
 <span data-ttu-id="6b164-125">Mostra come implementare i controlli con multithreading.</span><span class="sxs-lookup"><span data-stu-id="6b164-125">Shows how to implement multithreaded controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6b164-126">Riferimento</span><span class="sxs-lookup"><span data-stu-id="6b164-126">Reference</span></span>  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 <span data-ttu-id="6b164-127">Descrive la classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="6b164-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 <span data-ttu-id="6b164-128">Descrive la classe e include collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="6b164-128">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6b164-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="6b164-129">Related Sections</span></span>  
 [<span data-ttu-id="6b164-130">Attributi per componenti in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="6b164-130">Design-Time Attributes for Components</span></span>](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)  
 <span data-ttu-id="6b164-131">Elenca gli attributi dei metadati da applicare ai componenti e ai controlli in modo che vengano visualizzati correttamente in fase di progettazione nelle finestre di progettazione visiva.</span><span class="sxs-lookup"><span data-stu-id="6b164-131">Lists metadata attributes to apply to components and controls so that they are displayed correctly at design time in visual designers.</span></span>  
  
 [<span data-ttu-id="6b164-132">Estensione del supporto in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="6b164-132">Extending Design-Time Support</span></span>](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 <span data-ttu-id="6b164-133">Descrive come implementare classi, quali editor e finestre di progettazione, che forniscono supporto in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="6b164-133">Describes how to implement classes such as editors and designers that provide design-time support.</span></span>  
  
 [<span data-ttu-id="6b164-134">Procedura: concedere in licenza componenti e controlli</span><span class="sxs-lookup"><span data-stu-id="6b164-134">How to: License Components and Controls</span></span>](http://msdn.microsoft.com/library/8e66c1ed-a445-4b26-8185-990b6e2bbd57)  
 <span data-ttu-id="6b164-135">Descrive come implementare le licenze nel controllo o nel componente.</span><span class="sxs-lookup"><span data-stu-id="6b164-135">Describes how to implement licensing in your control or component.</span></span>  
  
 <span data-ttu-id="6b164-136">Vedere anche [Sviluppo di controlli Windows Form in fase di progettazione](http://msdn.microsoft.com/library/w29y3h59\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="6b164-136">Also see [Developing Windows Forms Controls at Design Time](http://msdn.microsoft.com/library/w29y3h59\(v=vs.110\)).</span></span>
