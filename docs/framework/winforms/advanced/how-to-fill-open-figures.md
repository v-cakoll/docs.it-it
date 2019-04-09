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
ms.openlocfilehash: addcf959e429974b9306353abb743bb2bb3114e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174564"
---
# <a name="how-to-fill-open-figures"></a>Procedura: Riempire figure aperte
È possibile compilare un percorso passando un <xref:System.Drawing.Drawing2D.GraphicsPath> dell'oggetto per il <xref:System.Drawing.Graphics.FillPath%2A> (metodo). Il <xref:System.Drawing.Graphics.FillPath%2A> metodo inserisce il percorso secondo la modalità di riempimento (alternativo o dei vertici) attualmente impostato per il percorso. Se il percorso include figure aperte, il percorso viene inserito come se fossero chiuse. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] chiude una figura tracciando una linea retta tra il punto finale al punto di partenza.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea un percorso che abbia una figura aperta (un arco) e una figura chiusa (un'ellisse). Il <xref:System.Drawing.Graphics.FillPath%2A> metodo inserisce il percorso secondo la modalità di riempimento predefinito, ovvero <xref:System.Drawing.Drawing2D.FillMode.Alternate>.  
  
 Nella figura seguente mostra l'output del codice di esempio. Si noti che il percorso viene riempito (in base alla <xref:System.Drawing.Drawing2D.FillMode.Alternate>) come se nella figura open sono stati chiusi da una linea retta tra il punto finale al punto di partenza.  
  
 ![Diagramma che mostra l'output del metodo FillPath](./media/how-to-fill-open-figures/fill-path-alternate-mode.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [Percorsi di oggetti Graphics in GDI+](graphics-paths-in-gdi.md)
