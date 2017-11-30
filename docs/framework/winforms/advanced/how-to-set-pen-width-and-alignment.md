---
title: 'Procedura: impostare la larghezza e l''allineamento di un oggetto Pen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6ed2a28c49554c686abb5e2635ab35b746b83465
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="ad5aa-102">Procedura: impostare la larghezza e l'allineamento di un oggetto Pen</span><span class="sxs-lookup"><span data-stu-id="ad5aa-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="ad5aa-103">Quando si crea un <xref:System.Drawing.Pen>, è possibile fornire la larghezza della penna come uno degli argomenti del costruttore.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="ad5aa-104">È inoltre possibile modificare la larghezza della penna con il <xref:System.Drawing.Pen.Width%2A> proprietà la <xref:System.Drawing.Pen> classe.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="ad5aa-105">Una linea teorica ha una larghezza pari a 0.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="ad5aa-106">Quando si disegna una riga con larghezza pari a 1 pixel, alla linea teorica sono incentrati i pixel.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="ad5aa-107">Se si disegna una linea più di un pixel di larghezza, i pixel sono centrati rispetto alla linea teorica o vengono visualizzati su un lato della linea teorica.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="ad5aa-108">È possibile impostare la proprietà di allineamento della penna di un <xref:System.Drawing.Pen> per determinare la posizione relativa alle linee teoriche dei pixel disegnati con quella penna.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="ad5aa-109">I valori <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, e <xref:System.Drawing.Drawing2D.PenAlignment.Inset> visualizzati di seguito esempi di codice sono membri del <xref:System.Drawing.Drawing2D.PenAlignment> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="ad5aa-110">Nell'esempio seguente disegna una linea due volte: una volta con una penna nera della larghezza di 1 e una volta con una penna verde di larghezza 10.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="ad5aa-111">Per variare lo spessore di un oggetto pen</span><span class="sxs-lookup"><span data-stu-id="ad5aa-111">To vary the width of a pen</span></span>  
  
-   <span data-ttu-id="ad5aa-112">Impostare il valore della <xref:System.Drawing.Pen.Alignment%2A> proprietà <xref:System.Drawing.Drawing2D.PenAlignment.Center> (predefinito) per specificare che la linea teorica verrà centrata pixel viene disegnata con la penna di colore verde.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="ad5aa-113">Nella figura seguente mostra la riga risulta.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-113">The following illustration shows the resulting line.</span></span>  
  
     <span data-ttu-id="ad5aa-114">![Penne](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")</span><span class="sxs-lookup"><span data-stu-id="ad5aa-114">![Pens](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")</span></span>  
  
     <span data-ttu-id="ad5aa-115">Nell'esempio seguente disegna un rettangolo due volte: una volta con una penna nera della larghezza di 1 e una volta con una penna verde di larghezza 10.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="ad5aa-116">Per modificare l'allineamento di un oggetto pen</span><span class="sxs-lookup"><span data-stu-id="ad5aa-116">To change the alignment of a pen</span></span>  
  
-   <span data-ttu-id="ad5aa-117">Impostare il valore della <xref:System.Drawing.Pen.Alignment%2A> proprietà <xref:System.Drawing.Drawing2D.PenAlignment.Center> per specificare che verrà centrata in corrispondenza del limite del rettangolo di pixel viene disegnata con la penna di colore verde.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="ad5aa-118">Nella figura seguente viene illustrato il rettangolo risulta.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-118">The following illustration shows the resulting rectangle.</span></span>  
  
     <span data-ttu-id="ad5aa-119">![Penne](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")</span><span class="sxs-lookup"><span data-stu-id="ad5aa-119">![Pens](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="ad5aa-120">Per creare la penna di inserimento</span><span class="sxs-lookup"><span data-stu-id="ad5aa-120">To create an inset pen</span></span>  
  
-   <span data-ttu-id="ad5aa-121">Modificare l'allineamento della penna verde modificando la terza istruzione nell'esempio di codice precedente come segue:</span><span class="sxs-lookup"><span data-stu-id="ad5aa-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="ad5aa-122">Il pixel in linea verde più larga appaiono all'interno del rettangolo come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="ad5aa-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="ad5aa-123">![Penne](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")</span><span class="sxs-lookup"><span data-stu-id="ad5aa-123">![Pens](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad5aa-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad5aa-124">See Also</span></span>  
 [<span data-ttu-id="ad5aa-125">Uso di un oggetto Pen per creare linee e forme</span><span class="sxs-lookup"><span data-stu-id="ad5aa-125">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="ad5aa-126">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="ad5aa-126">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
