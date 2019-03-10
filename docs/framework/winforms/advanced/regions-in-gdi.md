---
title: Regioni in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
ms.openlocfilehash: 31c0e4b1509c478786d075b127f0b181d5cdd1c6
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724973"
---
# <a name="regions-in-gdi"></a>Regioni in GDI+
Un'area è una parte dell'area di visualizzazione di un dispositivo di output. Aree possono essere complesso (una combinazione di Polygon e curve chiuse) o semplice (un rettangolo singolo). La figura seguente mostra due aree: uno creato da un rettangolo, e l'altro creato da un percorso.  
  
 ![Regions](./media/aboutgdip02-art27.gif "AboutGdip02_Art27")  
  
## <a name="using-regions"></a>Utilizzo delle regioni  
 Le aree vengono spesso usate per il ritaglio e l'hit testing. Ritaglio comporta la limitazione di disegno per una determinata area dell'area di visualizzazione, in genere la parte che deve essere aggiornato. Hit test prevedono la verifica per determinare se il cursore si trova in una determinata area dello schermo quando viene premuto un pulsante del mouse.  
  
 È possibile creare un'area da un rettangolo o un percorso. È anche possibile creare aree complesse combinando aree esistenti. Il <xref:System.Drawing.Region> classe fornisce metodi per la combinazione delle aree seguenti: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, e <xref:System.Drawing.Region.Complement%2A>.  
  
 L'intersezione di due aree geografiche è il set di tutti i punti che appartengono a entrambe le aree. L'unione è il set di tutti i punti che appartengono a uno o l'altro o entrambe le aree. Il complemento di un'area è il set di tutti i punti che non sono presenti nell'area. La figura seguente mostra l'intersezione e l'unione delle due aree illustrato nella figura precedente.  
  
 ![Regions](./media/aboutgdip02-art28.gif "AboutGdip02_Art28")  
  
 Il <xref:System.Drawing.Region.Xor%2A> metodo, applicato a una coppia di aree, produce un'area che contiene tutti i punti che appartengono a un'area o l'altro, ma non entrambi. Il <xref:System.Drawing.Region.Exclude%2A> metodo, applicato a una coppia di aree, produce un'area che contiene tutti i punti della prima area che non sono presenti nella seconda area. La figura seguente mostra le aree ottenuto dall'applicazione il <xref:System.Drawing.Region.Xor%2A> e <xref:System.Drawing.Region.Exclude%2A> metodi alle due aree mostrate all'inizio di questo argomento.  
  
 ![Regions](./media/aboutgdip02-art29.gif "AboutGdip02_Art29")  
  
 Per riempire un'area, è necessario un <xref:System.Drawing.Graphics> oggetti, una <xref:System.Drawing.Brush> oggetti e un <xref:System.Drawing.Region> oggetto. Il <xref:System.Drawing.Graphics> oggetto fornisce le <xref:System.Drawing.Graphics.FillRegion%2A> metodo e il <xref:System.Drawing.Brush> oggetto archivia gli attributi del riempimento, ad esempio colori o modello. Nell'esempio seguente riempie un'area con colori a tinta unita.  
  
 [!code-csharp[LinesCurvesAndShapes#61](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Drawing.Region?displayProperty=nameWithType>
- [Linee, curve e forme](lines-curves-and-shapes.md)
- [Uso delle regioni](using-regions.md)
