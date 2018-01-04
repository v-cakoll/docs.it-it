---
title: 'Procedura: riempire una forma con un motivo a tratteggio'
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
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f44289b79812f2330639cc333727bd21b6ef4fe6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="71fb5-102">Procedura: riempire una forma con un motivo a tratteggio</span><span class="sxs-lookup"><span data-stu-id="71fb5-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="71fb5-103">Un motivo a tratteggio è composto da due colori: uno per lo sfondo e uno per le righe che formano il modello sullo sfondo.</span><span class="sxs-lookup"><span data-stu-id="71fb5-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="71fb5-104">Per riempire una forma chiusa con un motivo a tratteggio, utilizzare un <xref:System.Drawing.Drawing2D.HatchBrush> oggetto.</span><span class="sxs-lookup"><span data-stu-id="71fb5-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="71fb5-105">Nell'esempio riportato di seguito viene illustrato come compilare un'ellisse con un motivo a tratteggio:</span><span class="sxs-lookup"><span data-stu-id="71fb5-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="71fb5-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="71fb5-106">Example</span></span>  
 <span data-ttu-id="71fb5-107">Il <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> costruttore accetta tre argomenti: il colore di sfondo, il colore della linea di tratteggio e lo stile di tratteggio.</span><span class="sxs-lookup"><span data-stu-id="71fb5-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="71fb5-108">L'argomento dello stile di tratteggio può essere un valore compreso tra il <xref:System.Drawing.Drawing2D.HatchStyle> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="71fb5-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="71fb5-109">Sono presenti più di 50 elementi di <xref:System.Drawing.Drawing2D.HatchStyle> enumerazione; alcuni di questi elementi sono visualizzati nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="71fb5-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="71fb5-110">Nella figura seguente mostra l'ellisse piena.</span><span class="sxs-lookup"><span data-stu-id="71fb5-110">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="71fb5-111">![Motivo di tratteggio](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="71fb5-111">![Hatch Pattern](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="71fb5-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="71fb5-112">Compiling the Code</span></span>  
 <span data-ttu-id="71fb5-113">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="71fb5-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71fb5-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71fb5-114">See Also</span></span>  
 [<span data-ttu-id="71fb5-115">Uso di un oggetto Brush per il riempimento di forme</span><span class="sxs-lookup"><span data-stu-id="71fb5-115">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
