---
title: 'Procedura: Disegnare una linea tratteggiata personalizzata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
ms.openlocfilehash: 77b4b959523c6d35dece2d759eeb71be04b53d93
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538622"
---
# <a name="how-to-draw-a-custom-dashed-line"></a><span data-ttu-id="c2304-102">Procedura: Disegnare una linea tratteggiata personalizzata</span><span class="sxs-lookup"><span data-stu-id="c2304-102">How to: Draw a Custom Dashed Line</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="c2304-103">fornisce diversi stili di tratteggio elencati nel <xref:System.Drawing.Drawing2D.DashStyle> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c2304-103">provides several dash styles that are listed in the <xref:System.Drawing.Drawing2D.DashStyle> enumeration.</span></span> <span data-ttu-id="c2304-104">Se questi stili di tratteggio standard non soddisfano le proprie esigenze, è possibile creare un motivo a tratteggio personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c2304-104">If those standard dash styles do not suit your needs, you can create a custom dash pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2304-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="c2304-105">Example</span></span>  
 <span data-ttu-id="c2304-106">Per disegnare una linea tratteggiata personalizzata, inserire le lunghezze dei trattini e spazi in una matrice e assegnare la matrice come valore dei <xref:System.Drawing.Pen.DashPattern%2A> proprietà di un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="c2304-106">To draw a custom dashed line, put the lengths of the dashes and spaces in an array and assign the array as the value of the <xref:System.Drawing.Pen.DashPattern%2A> property of a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="c2304-107">L'esempio seguente disegna una linea tratteggiata personalizzata in base alla matrice `{5, 2, 15, 4}`.</span><span class="sxs-lookup"><span data-stu-id="c2304-107">The following example draws a custom dashed line based on the array `{5, 2, 15, 4}`.</span></span> <span data-ttu-id="c2304-108">Se si moltiplica gli elementi della matrice in base alla larghezza della penna pari a 5, otterrai `{25, 10, 75, 20}`.</span><span class="sxs-lookup"><span data-stu-id="c2304-108">If you multiply the elements of the array by the pen width of 5, you get `{25, 10, 75, 20}`.</span></span> <span data-ttu-id="c2304-109">I trattini visualizzati alternano lunghezza compresa tra 25 e 75, mentre gli spazi lunghezza compresa tra 10 e 20.</span><span class="sxs-lookup"><span data-stu-id="c2304-109">The displayed dashes alternate in length between 25 and 75, and the spaces alternate in length between 10 and 20.</span></span>  
  
 <span data-ttu-id="c2304-110">La figura seguente mostra la linea tratteggiata risultante.</span><span class="sxs-lookup"><span data-stu-id="c2304-110">The following illustration shows the resulting dashed line.</span></span> <span data-ttu-id="c2304-111">Si noti che il trattino finale deve essere inferiore a 25 unità in modo che possa terminare la riga (405, 5).</span><span class="sxs-lookup"><span data-stu-id="c2304-111">Note that the final dash has to be shorter than 25 units so that the line can end at (405, 5).</span></span>  
  
 <span data-ttu-id="c2304-112">![Penne](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")</span><span class="sxs-lookup"><span data-stu-id="c2304-112">![Pens](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c2304-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="c2304-113">Compiling the Code</span></span>  
 <span data-ttu-id="c2304-114">Creare un modulo di Windows e la gestione del modulo <xref:System.Windows.Forms.Control.Paint> evento.</span><span class="sxs-lookup"><span data-stu-id="c2304-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="c2304-115">Incollare il codice precedente nel <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c2304-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2304-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2304-116">See also</span></span>
- [<span data-ttu-id="c2304-117">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="c2304-117">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
