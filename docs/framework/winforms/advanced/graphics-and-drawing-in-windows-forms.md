---
title: Grafica e disegno in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: e110203605c31f90f71c949f81c18ebf464d52eb
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505550"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="5773d-102">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="5773d-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="5773d-103">Common language runtime usa un'implementazione di Windows interfaccia GDI (Graphics Device) denominata GDI+ avanzata.</span><span class="sxs-lookup"><span data-stu-id="5773d-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface (GDI) called GDI+.</span></span> <span data-ttu-id="5773d-104">Con GDI+ è possibile creare grafici, disegnare il testo e modificare immagini grafiche come oggetti.</span><span class="sxs-lookup"><span data-stu-id="5773d-104">With GDI+ you can create graphics, draw text, and manipulate graphical images as objects.</span></span> <span data-ttu-id="5773d-105">GDI+ è progettato per offrire prestazioni e semplicità d'uso.</span><span class="sxs-lookup"><span data-stu-id="5773d-105">GDI+ is designed to offer performance and ease of use.</span></span> <span data-ttu-id="5773d-106">È possibile utilizzare GDI+ per eseguire il rendering di immagini grafiche in Windows Form e controlli.</span><span class="sxs-lookup"><span data-stu-id="5773d-106">You can use GDI+ to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="5773d-107">Sebbene sia possibile usare GDI+ direttamente nei Web Form, è possibile visualizzare immagini grafiche tramite il controllo Server Web Image.</span><span class="sxs-lookup"><span data-stu-id="5773d-107">Although you cannot use GDI+ directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="5773d-108">In questa sezione sono disponibili argomenti che illustrano i concetti fondamentali della programmazione in GDI+.</span><span class="sxs-lookup"><span data-stu-id="5773d-108">In this section, you will find topics that introduce the fundamentals of GDI+ programming.</span></span> <span data-ttu-id="5773d-109">Anche se non è da considerarsi come un riferimento esaustivo, la sezione contiene informazioni sugli oggetti <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> e <xref:System.Drawing.Color> e riporta informazioni su come creare forme, testo o visualizzare immagini.</span><span class="sxs-lookup"><span data-stu-id="5773d-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="5773d-110">Per altre informazioni, vedere [riferimento per GDI+](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span><span class="sxs-lookup"><span data-stu-id="5773d-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="5773d-111">Se si preferisce iniziare subito, vedere [Guida introduttiva alla programmazione grafica](getting-started-with-graphics-programming.md),</span><span class="sxs-lookup"><span data-stu-id="5773d-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="5773d-112">che include argomenti su come usare il codice per disegnare linee, forme, testo e altro in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="5773d-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5773d-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="5773d-113">In This Section</span></span>  
 [<span data-ttu-id="5773d-114">Cenni preliminari sulla grafica</span><span class="sxs-lookup"><span data-stu-id="5773d-114">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="5773d-115">Fornisce un'introduzione alle classi gestite relative agli elementi grafici.</span><span class="sxs-lookup"><span data-stu-id="5773d-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="5773d-116">Informazioni sul codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="5773d-116">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="5773d-117">Vengono fornite informazioni sulle classi gestite GDI+.</span><span class="sxs-lookup"><span data-stu-id="5773d-117">Provides information about the managed GDI+ classes.</span></span>  
  
 [<span data-ttu-id="5773d-118">Uso di classi grafiche gestite</span><span class="sxs-lookup"><span data-stu-id="5773d-118">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="5773d-119">Viene illustrato come a completata una serie di attività usando il GDI+ classi gestite.</span><span class="sxs-lookup"><span data-stu-id="5773d-119">Demonstrates how to complete a variety of tasks using the GDI+ managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5773d-120">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="5773d-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="5773d-121">Fornisce accesso alle funzionalità grafiche di base GDI+.</span><span class="sxs-lookup"><span data-stu-id="5773d-121">Provides access to GDI+ basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="5773d-122">Fornisce funzionalità grafica vettoriale e bidimensionale avanzata.</span><span class="sxs-lookup"><span data-stu-id="5773d-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="5773d-123">Fornisce funzionalità di imaging GDI+ avanzate.</span><span class="sxs-lookup"><span data-stu-id="5773d-123">Provides advanced GDI+ imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="5773d-124">Fornisce funzionalità tipografiche GDI+ avanzate.</span><span class="sxs-lookup"><span data-stu-id="5773d-124">Provides advanced GDI+ typography functionality.</span></span> <span data-ttu-id="5773d-125">Le classi presenti in questo spazio dei nomi consentono la creazione e l'uso di raccolte di tipi di carattere.</span><span class="sxs-lookup"><span data-stu-id="5773d-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="5773d-126">Fornisce funzionalità di stampa.</span><span class="sxs-lookup"><span data-stu-id="5773d-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5773d-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="5773d-127">Related Sections</span></span>  
 [<span data-ttu-id="5773d-128">Disegno e rendering di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="5773d-128">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="5773d-129">Spiega in dettaglio come fornire codice per i controlli di disegno.</span><span class="sxs-lookup"><span data-stu-id="5773d-129">Details how to provide code for painting controls.</span></span>
