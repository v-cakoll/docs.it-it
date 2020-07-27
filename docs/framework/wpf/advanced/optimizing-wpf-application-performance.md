---
title: Ottimizzare le prestazioni dell'app
description: Queste risorse consentono di migliorare le prestazioni delle applicazioni Windows Presentation Foundation, ad esempio la pianificazione delle prestazioni e l'utilizzo dell'hardware.
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 165caaf102a66988db0254839a947b8e262a386d
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166334"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="166d6-103">Ottimizzazione delle prestazioni di applicazioni WPF</span><span class="sxs-lookup"><span data-stu-id="166d6-103">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="166d6-104">Questa sezione è destinata a un riferimento per [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] gli sviluppatori di applicazioni che cercano modi per migliorare le prestazioni delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="166d6-104">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="166d6-105">Gli sviluppatori che non hanno familiarità con il Microsoft .NET Framework e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] devono prima di tutto acquisire familiarità con entrambe le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="166d6-105">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="166d6-106">Questa sezione presuppone la conoscenza del funzionamento di entrambi e viene scritta per i programmatori che conoscono già abbastanza per far funzionare le proprie applicazioni.</span><span class="sxs-lookup"><span data-stu-id="166d6-106">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="166d6-107">I dati sulle prestazioni forniti in questa sezione si basano sulle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni in esecuzione su un PC a 2,8 GHz con 512 RAM e una scheda grafica ATI Radeon 9700.</span><span class="sxs-lookup"><span data-stu-id="166d6-107">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="166d6-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="166d6-108">In This Section</span></span>  
 [<span data-ttu-id="166d6-109">Pianificazione delle prestazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="166d6-109">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="166d6-110">Sfruttare appieno l'hardware</span><span class="sxs-lookup"><span data-stu-id="166d6-110">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="166d6-111">Layout e progettazione</span><span class="sxs-lookup"><span data-stu-id="166d6-111">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="166d6-112">Grafica 2D e creazione di immagini</span><span class="sxs-lookup"><span data-stu-id="166d6-112">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="166d6-113">Comportamento degli oggetti</span><span class="sxs-lookup"><span data-stu-id="166d6-113">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="166d6-114">Risorse dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="166d6-114">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="166d6-115">Text</span><span class="sxs-lookup"><span data-stu-id="166d6-115">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="166d6-116">Data Binding</span><span class="sxs-lookup"><span data-stu-id="166d6-116">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="166d6-117">Controlli</span><span class="sxs-lookup"><span data-stu-id="166d6-117">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="166d6-118">Altri suggerimenti relativi alle prestazioni</span><span class="sxs-lookup"><span data-stu-id="166d6-118">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="166d6-119">Tempo di avvio delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="166d6-119">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="166d6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="166d6-120">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="166d6-121">Livelli di rendering della grafica</span><span class="sxs-lookup"><span data-stu-id="166d6-121">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="166d6-122">Cenni preliminari sul rendering della grafica WPF</span><span class="sxs-lookup"><span data-stu-id="166d6-122">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="166d6-123">Layout</span><span class="sxs-lookup"><span data-stu-id="166d6-123">Layout</span></span>](layout.md)
- [<span data-ttu-id="166d6-124">Strutture ad albero in WPF</span><span class="sxs-lookup"><span data-stu-id="166d6-124">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="166d6-125">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="166d6-125">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="166d6-126">Utilizzo degli oggetti DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="166d6-126">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="166d6-127">Cenni preliminari sulle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="166d6-127">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="166d6-128">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="166d6-128">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="166d6-129">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="166d6-129">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="166d6-130">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="166d6-130">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="166d6-131">Disegno di testo formattato</span><span class="sxs-lookup"><span data-stu-id="166d6-131">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="166d6-132">Funzionalità tipografiche di WPF</span><span class="sxs-lookup"><span data-stu-id="166d6-132">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="166d6-133">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="166d6-133">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="166d6-134">Cenni preliminari sulla navigazione</span><span class="sxs-lookup"><span data-stu-id="166d6-134">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="166d6-135">Suggerimenti sulle animazioni</span><span class="sxs-lookup"><span data-stu-id="166d6-135">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="166d6-136">Procedura dettagliata: Memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="166d6-136">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
