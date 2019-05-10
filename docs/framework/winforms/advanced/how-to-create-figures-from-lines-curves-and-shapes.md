---
title: 'Procedura: Creare figure da linee, curve e forme'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: c8cf7a7e08bed56fb704bba4e30ff369bc3fcf89
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64643462"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>Procedura: Creare figure da linee, curve e forme
Per una figura di creare, costruire un <xref:System.Drawing.Drawing2D.GraphicsPath>, quindi chiamare i metodi, ad esempio <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> e <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, per aggiungere le primitive nel percorso.  
  
## <a name="example"></a>Esempio  
 Gli esempi di codice seguente creano i percorsi contenenti cifre:  
  
- Nel primo esempio crea un percorso che abbia una sola figura. Nella figura è costituito da un singolo arco. Punto finale dell'arco dispone di un angolo di apertura della-180 gradi, in senso antiorario nel sistema di coordinate predefinito.  
  
- Nel secondo esempio viene creato un percorso con due cifre. La prima figura fa un arco seguito da una riga. La seconda figura è una riga seguita da una curva seguita da una riga. La prima figura viene lasciata aperta, e la seconda figura è chiusa.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Negli esempi precedenti sono progettati per l'uso con Windows Form, e richiedono <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [Costruzione e creazione di percorsi](constructing-and-drawing-paths.md)
- [Uso di un oggetto Pen per creare linee e forme](using-a-pen-to-draw-lines-and-shapes.md)
