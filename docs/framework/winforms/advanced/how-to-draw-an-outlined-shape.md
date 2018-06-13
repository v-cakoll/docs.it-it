---
title: 'Procedura: creare una forma con contorno'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
ms.openlocfilehash: b674c4d80ba6c70c0bdff6d020527a039e5c7baa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521915"
---
# <a name="how-to-draw-an-outlined-shape"></a><span data-ttu-id="e10bd-102">Procedura: creare una forma con contorno</span><span class="sxs-lookup"><span data-stu-id="e10bd-102">How to: Draw an Outlined Shape</span></span>
<span data-ttu-id="e10bd-103">In questo esempio disegna ellissi e rettangoli in un form.</span><span class="sxs-lookup"><span data-stu-id="e10bd-103">This example draws outlined ellipses and rectangles on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e10bd-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e10bd-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e10bd-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e10bd-105">Compiling the Code</span></span>  
 <span data-ttu-id="e10bd-106">Non è possibile chiamare questo metodo <xref:System.Windows.Forms.Form.Load> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="e10bd-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="e10bd-107">Se il form viene ridimensionato o nascosto da un altro formato, il contenuto disegnato non verrà ridisegnato.</span><span class="sxs-lookup"><span data-stu-id="e10bd-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="e10bd-108">Per ridisegnare automaticamente il contenuto è necessario eseguire l'override di <xref:System.Windows.Forms.Control.OnPaint%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="e10bd-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e10bd-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="e10bd-109">Robust Programming</span></span>  
 <span data-ttu-id="e10bd-110">È necessario chiamare sempre <xref:System.IDisposable.Dispose%2A> in tutti gli oggetti che utilizzano le risorse di sistema, ad esempio <xref:System.Drawing.Pen> e <xref:System.Drawing.Graphics> oggetti.</span><span class="sxs-lookup"><span data-stu-id="e10bd-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e10bd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e10bd-111">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Drawing.Graphics.DrawRectangle%2A>  
 [<span data-ttu-id="e10bd-112">Introduzione alla programmazione grafica</span><span class="sxs-lookup"><span data-stu-id="e10bd-112">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="e10bd-113">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="e10bd-113">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="e10bd-114">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e10bd-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
