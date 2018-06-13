---
title: Ottimizzazione delle prestazioni di applicazioni WPF
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: faa06e4558401c1d0e9335fbc630c5371d1bc516
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546328"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="96eb5-102">Ottimizzazione delle prestazioni di applicazioni WPF</span><span class="sxs-lookup"><span data-stu-id="96eb5-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="96eb5-103">Questa sezione è destinata come riferimento per [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] gli sviluppatori di applicazioni che desiderano modi migliorare le prestazioni delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="96eb5-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="96eb5-104">Se si è uno sviluppatore che è una novità di Microsoft .NET Framework e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], è consigliabile acquisire familiarità con entrambe le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="96eb5-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="96eb5-105">In questa sezione presuppone una conoscenza di entrambi e viene scritto per i programmatori che già conoscono sufficiente per ottenere le applicazioni in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="96eb5-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96eb5-106">I dati sulle prestazioni disponibili in questa sezione si basano [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni in esecuzione in un PC a 2,8 GHz con 512 RAM e un ATI Radeon 9700 scheda grafica.</span><span class="sxs-lookup"><span data-stu-id="96eb5-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96eb5-107">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="96eb5-107">In This Section</span></span>  
 [<span data-ttu-id="96eb5-108">Pianificazione delle prestazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="96eb5-108">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
  
 [<span data-ttu-id="96eb5-109">Sfruttare appieno l'hardware</span><span class="sxs-lookup"><span data-stu-id="96eb5-109">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="96eb5-110">Ottimizzazione delle prestazioni: layout e progettazione</span><span class="sxs-lookup"><span data-stu-id="96eb5-110">Layout and Design</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="96eb5-111">Grafica bidimensionale e creazione di immagini</span><span class="sxs-lookup"><span data-stu-id="96eb5-111">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="96eb5-112">Comportamento dell'oggetto</span><span class="sxs-lookup"><span data-stu-id="96eb5-112">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="96eb5-113">Risorse di applicazioni</span><span class="sxs-lookup"><span data-stu-id="96eb5-113">Application Resources</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="96eb5-114">per</span><span class="sxs-lookup"><span data-stu-id="96eb5-114">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
  
 [<span data-ttu-id="96eb5-115">Data binding</span><span class="sxs-lookup"><span data-stu-id="96eb5-115">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="96eb5-116">Controlli</span><span class="sxs-lookup"><span data-stu-id="96eb5-116">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)  
  
 [<span data-ttu-id="96eb5-117">Altri suggerimenti relativi alle prestazioni</span><span class="sxs-lookup"><span data-stu-id="96eb5-117">Other Performance Recommendations</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="96eb5-118">Tempo di avvio delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="96eb5-118">Application Startup Time</span></span>](../../../../docs/framework/wpf/advanced/application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="96eb5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96eb5-119">See Also</span></span>  
 <xref:System.Windows.Media.RenderOptions>  
 <xref:System.Windows.Media.RenderCapability>  
 [<span data-ttu-id="96eb5-120">Livelli di rendering della grafica</span><span class="sxs-lookup"><span data-stu-id="96eb5-120">Graphics Rendering Tiers</span></span>](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)  
 [<span data-ttu-id="96eb5-121">Cenni preliminari sul rendering della grafica WPF</span><span class="sxs-lookup"><span data-stu-id="96eb5-121">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [<span data-ttu-id="96eb5-122">Layout</span><span class="sxs-lookup"><span data-stu-id="96eb5-122">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)  
 [<span data-ttu-id="96eb5-123">Strutture ad albero in WPF</span><span class="sxs-lookup"><span data-stu-id="96eb5-123">Trees in WPF</span></span>](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)  
 [<span data-ttu-id="96eb5-124">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="96eb5-124">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="96eb5-125">Uso degli oggetti DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="96eb5-125">Using DrawingVisual Objects</span></span>](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)  
 [<span data-ttu-id="96eb5-126">Panoramica sulle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="96eb5-126">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="96eb5-127">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="96eb5-127">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="96eb5-128">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="96eb5-128">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="96eb5-129">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="96eb5-129">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="96eb5-130">Disegno di testo formattato</span><span class="sxs-lookup"><span data-stu-id="96eb5-130">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)  
 [<span data-ttu-id="96eb5-131">Funzionalità tipografiche di WPF</span><span class="sxs-lookup"><span data-stu-id="96eb5-131">Typography in WPF</span></span>](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [<span data-ttu-id="96eb5-132">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="96eb5-132">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="96eb5-133">Cenni preliminari sulla navigazione</span><span class="sxs-lookup"><span data-stu-id="96eb5-133">Navigation Overview</span></span>](../../../../docs/framework/wpf/app-development/navigation-overview.md)  
 [<span data-ttu-id="96eb5-134">Suggerimenti sulle animazioni</span><span class="sxs-lookup"><span data-stu-id="96eb5-134">Animation Tips and Tricks</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)  
 [<span data-ttu-id="96eb5-135">Procedura dettagliata: Memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="96eb5-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-caching-application-data-in-a-wpf-application.md)
