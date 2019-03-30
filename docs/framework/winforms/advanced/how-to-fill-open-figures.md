---
title: 'Procedura: Riempire figure aperte'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: c7d193fdad554048ecd0f2cca5a83cfccbc2a403
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654081"
---
# <a name="how-to-fill-open-figures"></a><span data-ttu-id="8c183-102">Procedura: Riempire figure aperte</span><span class="sxs-lookup"><span data-stu-id="8c183-102">How to: Fill Open Figures</span></span>
<span data-ttu-id="8c183-103">È possibile compilare un percorso passando un <xref:System.Drawing.Drawing2D.GraphicsPath> dell'oggetto per il <xref:System.Drawing.Graphics.FillPath%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="8c183-103">You can fill a path by passing a <xref:System.Drawing.Drawing2D.GraphicsPath> object to the <xref:System.Drawing.Graphics.FillPath%2A> method.</span></span> <span data-ttu-id="8c183-104">Il <xref:System.Drawing.Graphics.FillPath%2A> metodo inserisce il percorso secondo la modalità di riempimento (alternativo o dei vertici) attualmente impostato per il percorso.</span><span class="sxs-lookup"><span data-stu-id="8c183-104">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the fill mode (alternate or winding) currently set for the path.</span></span> <span data-ttu-id="8c183-105">Se il percorso include figure aperte, il percorso viene inserito come se fossero chiuse.</span><span class="sxs-lookup"><span data-stu-id="8c183-105">If the path has any open figures, the path is filled as if those figures were closed.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="8c183-106">chiude una figura tracciando una linea retta tra il punto finale al punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="8c183-106">closes a figure by drawing a straight line from its ending point to its starting point.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c183-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c183-107">Example</span></span>  
 <span data-ttu-id="8c183-108">L'esempio seguente crea un percorso che abbia una figura aperta (un arco) e una figura chiusa (un'ellisse).</span><span class="sxs-lookup"><span data-stu-id="8c183-108">The following example creates a path that has one open figure (an arc) and one closed figure (an ellipse).</span></span> <span data-ttu-id="8c183-109">Il <xref:System.Drawing.Graphics.FillPath%2A> metodo inserisce il percorso secondo la modalità di riempimento predefinito, ovvero <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span><span class="sxs-lookup"><span data-stu-id="8c183-109">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the default fill mode, which is <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span></span>  
  
 <span data-ttu-id="8c183-110">Nella figura seguente mostra l'output del codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="8c183-110">The following illustration shows the output of the example code.</span></span> <span data-ttu-id="8c183-111">Si noti che il percorso viene riempito (in base alla <xref:System.Drawing.Drawing2D.FillMode.Alternate>) come se nella figura open sono stati chiusi da una linea retta tra il punto finale al punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="8c183-111">Note that the path is filled (according to <xref:System.Drawing.Drawing2D.FillMode.Alternate>) as if the open figure were closed by a straight line from its ending point to its starting point.</span></span>  
  
 ![Diagramma che mostra l'output del metodo FillPath](./media/how-to-fill-open-figures/fill-path-alternate-mode.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8c183-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="8c183-113">Compiling the Code</span></span>  
 <span data-ttu-id="8c183-114">L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="8c183-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c183-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c183-115">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="8c183-116">Percorsi di oggetti Graphics in GDI+</span><span class="sxs-lookup"><span data-stu-id="8c183-116">Graphics Paths in GDI+</span></span>](graphics-paths-in-gdi.md)
