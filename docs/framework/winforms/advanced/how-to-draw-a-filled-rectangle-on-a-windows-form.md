---
title: 'Procedura: Disegnare un rettangolo pieno in un Windows Form'
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
ms.openlocfilehash: e551eacf0924c9bffa802fb5d2ba8bae7c1c3a98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004302"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a><span data-ttu-id="0dd80-102">Procedura: Disegnare un rettangolo pieno in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="0dd80-102">How to: Draw a Filled Rectangle on a Windows Form</span></span>
<span data-ttu-id="0dd80-103">In questo esempio disegna un rettangolo pieno in un form.</span><span class="sxs-lookup"><span data-stu-id="0dd80-103">This example draws a filled rectangle on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0dd80-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0dd80-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0dd80-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0dd80-105">Compiling the Code</span></span>  
 <span data-ttu-id="0dd80-106">È possibile chiamare questo metodo nel <xref:System.Windows.Forms.Form.Load> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="0dd80-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="0dd80-107">Il contenuto creato non verrà ridisegnato se il form viene ridimensionato o nascosto da un altro form.</span><span class="sxs-lookup"><span data-stu-id="0dd80-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="0dd80-108">Per rendere il contenuto viene ridisegnata automaticamente, è necessario eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="0dd80-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0dd80-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="0dd80-109">Robust Programming</span></span>  
 <span data-ttu-id="0dd80-110">È sempre necessario chiamare <xref:System.IDisposable.Dispose%2A> tutti gli oggetti che utilizzano le risorse di sistema, ad esempio <xref:System.Drawing.Brush> e <xref:System.Drawing.Graphics> oggetti.</span><span class="sxs-lookup"><span data-stu-id="0dd80-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dd80-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0dd80-111">See also</span></span>

- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="0dd80-112">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="0dd80-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="0dd80-113">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="0dd80-113">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="0dd80-114">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="0dd80-114">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="0dd80-115">Pennelli e forme con riempimento in GDI+</span><span class="sxs-lookup"><span data-stu-id="0dd80-115">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
