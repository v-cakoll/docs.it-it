---
title: 'Procedura: disegnare un rettangolo con riempimento in un Windows Form'
description: Informazioni su come creare un rettangolo pieno in un Windows Form a livello di codice. Altre informazioni sulla compilazione del codice.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
ms.openlocfilehash: 0ad8ec97000e29b2194a9eda713aa43d5557b44c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621639"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a><span data-ttu-id="e1703-104">Procedura: disegnare un rettangolo con riempimento in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="e1703-104">How to: Draw a Filled Rectangle on a Windows Form</span></span>
<span data-ttu-id="e1703-105">Questo esempio disegna un rettangolo pieno in un form.</span><span class="sxs-lookup"><span data-stu-id="e1703-105">This example draws a filled rectangle on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1703-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1703-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e1703-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e1703-107">Compiling the Code</span></span>  
 <span data-ttu-id="e1703-108">Non è possibile chiamare questo metodo nel <xref:System.Windows.Forms.Form.Load> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="e1703-108">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="e1703-109">Il contenuto disegnato non verrà ridisegnato se il form viene ridimensionato o nascosto da un altro form.</span><span class="sxs-lookup"><span data-stu-id="e1703-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="e1703-110">Per ridisegnare automaticamente il contenuto, è necessario eseguire l'override del <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="e1703-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e1703-111">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="e1703-111">Robust Programming</span></span>  
 <span data-ttu-id="e1703-112">È sempre necessario chiamare <xref:System.IDisposable.Dispose%2A> sugli oggetti che utilizzano le risorse di sistema, ad <xref:System.Drawing.Brush> esempio <xref:System.Drawing.Graphics> gli oggetti e.</span><span class="sxs-lookup"><span data-stu-id="e1703-112">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1703-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1703-113">See also</span></span>

- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="e1703-114">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="e1703-114">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="e1703-115">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e1703-115">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="e1703-116">Uso di una penna per disegnare linee e forme</span><span class="sxs-lookup"><span data-stu-id="e1703-116">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="e1703-117">Pennelli e forme con riempimento in GDI+</span><span class="sxs-lookup"><span data-stu-id="e1703-117">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
