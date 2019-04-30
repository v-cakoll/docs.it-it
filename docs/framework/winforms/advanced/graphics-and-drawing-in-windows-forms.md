---
title: Grafica e disegno in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 08f87436ade62bb54295b012a1c24dc177ea9667
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938177"
---
# <a name="graphics-and-drawing-in-windows-forms"></a><span data-ttu-id="c61d2-102">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c61d2-102">Graphics and Drawing in Windows Forms</span></span>
<span data-ttu-id="c61d2-103">Common Language Runtime usa un'implementazione avanzata dell'interfaccia Graphics Device Interface ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) di Windows, denominata [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c61d2-103">The common language runtime uses an advanced implementation of the Windows Graphics Device Interface ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) called [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="c61d2-104">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] consente di creare grafici, testo e di manipolare le immagini come oggetti.</span><span class="sxs-lookup"><span data-stu-id="c61d2-104">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] you can create graphics, draw text, and manipulate graphical images as objects.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="c61d2-105">è stato progettato in modo da garantire prestazioni elevate ed è caratterizzato da un'estrema facilità d'uso.</span><span class="sxs-lookup"><span data-stu-id="c61d2-105">is designed to offer performance and ease of use.</span></span> <span data-ttu-id="c61d2-106">È possibile usare [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per eseguire il rendering di immagini grafiche in Windows Form e nei relativi controlli.</span><span class="sxs-lookup"><span data-stu-id="c61d2-106">You can use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to render graphical images on Windows Forms and controls.</span></span> <span data-ttu-id="c61d2-107">Anche se non è possibile usare [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] direttamente in Web Form, è comunque possibile visualizzare immagini grafiche tramite il controllo server Web Image.</span><span class="sxs-lookup"><span data-stu-id="c61d2-107">Although you cannot use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] directly on Web Forms, you can display graphical images through the Image Web Server control.</span></span>  
  
 <span data-ttu-id="c61d2-108">Questa sezione comprende argomenti in cui vengono presentati i principi fondamentali della programmazione [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c61d2-108">In this section, you will find topics that introduce the fundamentals of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] programming.</span></span> <span data-ttu-id="c61d2-109">Anche se non è da considerarsi come un riferimento esaustivo, la sezione contiene informazioni sugli oggetti <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> e <xref:System.Drawing.Color> e riporta informazioni su come creare forme, testo o visualizzare immagini.</span><span class="sxs-lookup"><span data-stu-id="c61d2-109">Although not intended to be a comprehensive reference, this section includes information about the <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush>, and <xref:System.Drawing.Color> objects, and explains how to perform such tasks as drawing shapes, drawing text, or displaying images.</span></span> <span data-ttu-id="c61d2-110">Per altre informazioni, vedere [riferimento per GDI+](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span><span class="sxs-lookup"><span data-stu-id="c61d2-110">For more information, see [GDI+ Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).</span></span>  
  
 <span data-ttu-id="c61d2-111">Se si preferisce iniziare subito, vedere [Guida introduttiva alla programmazione grafica](getting-started-with-graphics-programming.md),</span><span class="sxs-lookup"><span data-stu-id="c61d2-111">If you'd like to jump in and get started right away, see [Getting Started with Graphics Programming](getting-started-with-graphics-programming.md).</span></span> <span data-ttu-id="c61d2-112">che include argomenti su come usare il codice per disegnare linee, forme, testo e altro in Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c61d2-112">It has topics on how to use code to draw lines, shapes, text, and more on Windows forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c61d2-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="c61d2-113">In This Section</span></span>  
 [<span data-ttu-id="c61d2-114">Cenni preliminari sulla grafica</span><span class="sxs-lookup"><span data-stu-id="c61d2-114">Graphics Overview</span></span>](graphics-overview-windows-forms.md)  
 <span data-ttu-id="c61d2-115">Fornisce un'introduzione alle classi gestite relative agli elementi grafici.</span><span class="sxs-lookup"><span data-stu-id="c61d2-115">Provides an introduction to the graphics-related managed classes.</span></span>  
  
 [<span data-ttu-id="c61d2-116">Informazioni sul codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="c61d2-116">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
 <span data-ttu-id="c61d2-117">Fornisce informazioni sulle classi [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] gestite.</span><span class="sxs-lookup"><span data-stu-id="c61d2-117">Provides information about the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span>  
  
 [<span data-ttu-id="c61d2-118">Uso di classi grafiche gestite</span><span class="sxs-lookup"><span data-stu-id="c61d2-118">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)  
 <span data-ttu-id="c61d2-119">Illustra come completare una serie di attività usando le classi gestite [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c61d2-119">Demonstrates how to complete a variety of tasks using the [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] managed classes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c61d2-120">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="c61d2-120">Reference</span></span>  
 <xref:System.Drawing>  
 <span data-ttu-id="c61d2-121">Fornisce accesso alle funzionalità grafiche di base di [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c61d2-121">Provides access to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] basic graphics functionality.</span></span>  
  
 <xref:System.Drawing.Drawing2D>  
 <span data-ttu-id="c61d2-122">Fornisce funzionalità grafica vettoriale e bidimensionale avanzata.</span><span class="sxs-lookup"><span data-stu-id="c61d2-122">Provides advanced two-dimensional and vector graphics functionality.</span></span>  
  
 <xref:System.Drawing.Imaging>  
 <span data-ttu-id="c61d2-123">Fornisce funzionalità avanzate [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per le immagini.</span><span class="sxs-lookup"><span data-stu-id="c61d2-123">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] imaging functionality.</span></span>  
  
 <xref:System.Drawing.Text>  
 <span data-ttu-id="c61d2-124">Fornisce funzionalità avanzate [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per la tipografia.</span><span class="sxs-lookup"><span data-stu-id="c61d2-124">Provides advanced [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] typography functionality.</span></span> <span data-ttu-id="c61d2-125">Le classi presenti in questo spazio dei nomi consentono la creazione e l'uso di raccolte di tipi di carattere.</span><span class="sxs-lookup"><span data-stu-id="c61d2-125">The classes in this namespace can be used to create and use collections of fonts.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="c61d2-126">Fornisce funzionalità di stampa.</span><span class="sxs-lookup"><span data-stu-id="c61d2-126">Provides printing functionality.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c61d2-127">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c61d2-127">Related Sections</span></span>  
 [<span data-ttu-id="c61d2-128">Disegno e rendering di controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="c61d2-128">Custom Control Painting and Rendering</span></span>](../controls/custom-control-painting-and-rendering.md)  
 <span data-ttu-id="c61d2-129">Spiega in dettaglio come fornire codice per i controlli di disegno.</span><span class="sxs-lookup"><span data-stu-id="c61d2-129">Details how to provide code for painting controls.</span></span>
