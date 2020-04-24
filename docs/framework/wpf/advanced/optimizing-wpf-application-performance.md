---
title: Ottimizzare le prestazioni dell'app
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 54d69e87ef2a9c5318e394422e3bcfcabcc76210
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646253"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="d2b94-102">Ottimizzazione delle prestazioni di applicazioni WPF</span><span class="sxs-lookup"><span data-stu-id="d2b94-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="d2b94-103">Questa sezione è intesa come riferimento per [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] gli sviluppatori di applicazioni che sono alla ricerca di modi per migliorare le prestazioni delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d2b94-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="d2b94-104">Se si è uno sviluppatore che non [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ha familiarità con Microsoft .NET Framework e , è necessario innanzitutto acquisire familiarità con entrambe le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="d2b94-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="d2b94-105">Questa sezione presuppone una conoscenza di entrambi ed è stata scritta per i programmatori che già conoscono abbastanza per mettere in funzione le loro applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d2b94-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2b94-106">I dati sulle prestazioni forniti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in questa sezione si basano su applicazioni in esecuzione su un PC da 2,8 GHz con 512 RAM e una scheda grafica ATI Radeon 9700.</span><span class="sxs-lookup"><span data-stu-id="d2b94-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d2b94-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d2b94-107">In This Section</span></span>  
 [<span data-ttu-id="d2b94-108">Pianificazione delle prestazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d2b94-108">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="d2b94-109">Sfruttare appieno l'hardware</span><span class="sxs-lookup"><span data-stu-id="d2b94-109">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="d2b94-110">Layout e progettazione</span><span class="sxs-lookup"><span data-stu-id="d2b94-110">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="d2b94-111">Grafica 2D e creazione di immagini</span><span class="sxs-lookup"><span data-stu-id="d2b94-111">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="d2b94-112">Comportamento degli oggetti</span><span class="sxs-lookup"><span data-stu-id="d2b94-112">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="d2b94-113">Risorse dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d2b94-113">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="d2b94-114">Text</span><span class="sxs-lookup"><span data-stu-id="d2b94-114">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="d2b94-115">Associazione dati</span><span class="sxs-lookup"><span data-stu-id="d2b94-115">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="d2b94-116">Controlli</span><span class="sxs-lookup"><span data-stu-id="d2b94-116">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="d2b94-117">Altri suggerimenti relativi alle prestazioni</span><span class="sxs-lookup"><span data-stu-id="d2b94-117">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="d2b94-118">Tempo di avvio delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="d2b94-118">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="d2b94-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2b94-119">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="d2b94-120">Livelli di rendering della grafica</span><span class="sxs-lookup"><span data-stu-id="d2b94-120">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="d2b94-121">Cenni preliminari sul rendering della grafica WPF</span><span class="sxs-lookup"><span data-stu-id="d2b94-121">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="d2b94-122">Layout</span><span class="sxs-lookup"><span data-stu-id="d2b94-122">Layout</span></span>](layout.md)
- [<span data-ttu-id="d2b94-123">Strutture ad albero in WPF</span><span class="sxs-lookup"><span data-stu-id="d2b94-123">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="d2b94-124">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="d2b94-124">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="d2b94-125">Utilizzo degli oggetti DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="d2b94-125">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="d2b94-126">Panoramica sulle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="d2b94-126">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="d2b94-127">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="d2b94-127">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="d2b94-128">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="d2b94-128">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="d2b94-129">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="d2b94-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="d2b94-130">Disegno di testo formattato</span><span class="sxs-lookup"><span data-stu-id="d2b94-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="d2b94-131">Funzionalità tipografiche di WPF</span><span class="sxs-lookup"><span data-stu-id="d2b94-131">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="d2b94-132">Cenni preliminari sull'associazione dati</span><span class="sxs-lookup"><span data-stu-id="d2b94-132">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="d2b94-133">Cenni preliminari sulla navigazione</span><span class="sxs-lookup"><span data-stu-id="d2b94-133">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="d2b94-134">Suggerimenti sulle animazioni</span><span class="sxs-lookup"><span data-stu-id="d2b94-134">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="d2b94-135">Procedura dettagliata: Memorizzazione dei dati di un'applicazione nella cache di un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="d2b94-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
