---
title: 'Procedura: riempire una forma con un motivo a tratteggio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: b80708f0ce722b1809fe49190639231e7e4c8329
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320063"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="00149-102">Procedura: riempire una forma con un motivo a tratteggio</span><span class="sxs-lookup"><span data-stu-id="00149-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="00149-103">Un modello di tratteggio è costituito da due colori: uno per lo sfondo e uno per le linee che formano il modello sullo sfondo.</span><span class="sxs-lookup"><span data-stu-id="00149-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="00149-104">Per riempire una forma chiusa con un motivo di tratteggio, usare un oggetto <xref:System.Drawing.Drawing2D.HatchBrush>.</span><span class="sxs-lookup"><span data-stu-id="00149-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="00149-105">Nell'esempio seguente viene illustrato come riempire un'ellisse con un motivo di tratteggio:</span><span class="sxs-lookup"><span data-stu-id="00149-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="00149-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="00149-106">Example</span></span>  
 <span data-ttu-id="00149-107">Il costruttore <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> accetta tre argomenti: lo stile di tratteggio, il colore della linea di tratteggio e il colore dello sfondo.</span><span class="sxs-lookup"><span data-stu-id="00149-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="00149-108">L'argomento dello stile di tratteggio può essere qualsiasi valore dell'enumerazione <xref:System.Drawing.Drawing2D.HatchStyle>.</span><span class="sxs-lookup"><span data-stu-id="00149-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="00149-109">Sono presenti più di 50 elementi nell'enumerazione <xref:System.Drawing.Drawing2D.HatchStyle>; alcuni di questi elementi sono illustrati nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="00149-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="00149-110">Nell'illustrazione seguente viene mostrata l'ellisse piena.</span><span class="sxs-lookup"><span data-stu-id="00149-110">The following illustration shows the filled ellipse.</span></span>  
  
  <span data-ttu-id="00149-111">![Screenshot dell'aspetto di un'ellisse riempita con un modello di tratteggio.](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="00149-111">![Screenshot of what an ellipse filled with a hatch pattern looks like.](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")</span></span>
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="00149-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="00149-112">Compiling the Code</span></span>  
 <span data-ttu-id="00149-113">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.</span><span class="sxs-lookup"><span data-stu-id="00149-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00149-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00149-114">See also</span></span>

- [<span data-ttu-id="00149-115">Uso di un oggetto Brush per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="00149-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
