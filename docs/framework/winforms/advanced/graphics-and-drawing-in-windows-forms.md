---
title: Grafica e disegno
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 10ad18d38c84f6e447601ab6c8bf1a953dabb7cf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746410"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="6ed2a-102">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="6ed2a-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="6ed2a-103">Il Common Language Runtime utilizza un'implementazione avanzata di Windows Graphics Device Interface (GDI) denominato GDI+.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="6ed2a-104">Con GDI+ è possibile creare grafica, creare testo e modificare immagini grafiche come oggetti.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-104">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="6ed2a-105">GDI+ è progettato per offrire prestazioni e facilità di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-105">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="6ed2a-106">È possibile utilizzare GDI+ per eseguire il rendering di immagini grafiche in Windows Forms e controlli.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-106">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="6ed2a-107">Sebbene non sia possibile utilizzare GDI+ direttamente nei Web Form, è possibile visualizzare immagini grafiche tramite il controllo server Web Image.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-107">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="6ed2a-108">In questa sezione sono disponibili argomenti che introducono le nozioni di base sulla programmazione GDI+.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-108">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="6ed2a-109">Anche se non è da considerarsi come un riferimento esaustivo, la sezione contiene informazioni sugli oggetti <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> e <xref:System.Drawing.Color> e riporta informazioni su come creare forme, testo o visualizzare immagini.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="6ed2a-110">Per ulteriori informazioni, vedere [riferimento a GDI+](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span><span class="sxs-lookup"><span data-stu-id="6ed2a-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="6ed2a-111">Se si preferisce iniziare subito, vedere [Guida introduttiva alla programmazione grafica](getting-started-with-graphics-programming.md),</span><span class="sxs-lookup"><span data-stu-id="6ed2a-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="6ed2a-112">che include argomenti su come usare il codice per disegnare linee, forme, testo e altro in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ed2a-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="6ed2a-113">In This Section</span></span>  
 [<span data-ttu-id="6ed2a-114">Cenni preliminari sulla grafica</span><span class="sxs-lookup"><span data-stu-id="6ed2a-114">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="6ed2a-115">Fornisce un'introduzione alle classi gestite relative agli elementi grafici.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="6ed2a-116">Informazioni sul codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="6ed2a-116">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="6ed2a-117">Fornisce informazioni sulle classi GDI+ gestite.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-117">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="6ed2a-118">Uso di classi grafiche gestite</span><span class="sxs-lookup"><span data-stu-id="6ed2a-118">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="6ed2a-119">Viene illustrato come completare una serie di attività usando le classi gestite GDI+.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-119">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6ed2a-120">Riferimento</span><span class="sxs-lookup"><span data-stu-id="6ed2a-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="6ed2a-121">Fornisce accesso alle funzionalità grafiche di base GDI+.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-121">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="6ed2a-122">Fornisce funzionalità grafica vettoriale e bidimensionale avanzata.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="6ed2a-123">Fornisce funzionalità avanzate per la creazione di immagini GDI+.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-123">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="6ed2a-124">Fornisce funzionalità tipografiche GDI+ avanzate.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-124">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="6ed2a-125">Le classi presenti in questo spazio dei nomi consentono la creazione e l'uso di raccolte di tipi di carattere.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="6ed2a-126">Fornisce funzionalità di stampa.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6ed2a-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="6ed2a-127">Related Sections</span></span>  
 [<span data-ttu-id="6ed2a-128">Disegno e rendering di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="6ed2a-128">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="6ed2a-129">Spiega in dettaglio come fornire codice per i controlli di disegno.</span><span class="sxs-lookup"><span data-stu-id="6ed2a-129">Details how to provide code for painting controls.</span></span>
