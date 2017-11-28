---
title: Regioni in GDI+
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
- GDI+, regions
- drawing [Windows Forms], regions
- regions
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0525e7b58353909d41e5367aa52a17aa56bcd77c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="regions-in-gdi"></a>Regioni in GDI+
Un'area è una parte dell'area di visualizzazione di un dispositivo di output. Aree possono essere semplice (un rettangolo singolo) o complesso (una combinazione di poligoni e curve chiuse). La figura seguente mostra due aree: una creata da un rettangolo e l'altro costruito da un percorso.  
  
 ![Aree](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.gif "AboutGdip02_Art27")  
  
## <a name="using-regions"></a>Utilizzo delle regioni  
 Le aree vengono spesso utilizzate per il ritaglio e l'hit test. Il ritaglio implica la restrizione di disegno per una determinata area geografica dell'area di visualizzazione, in genere la parte che deve essere aggiornato. Processo di hit testing implica il controllo per determinare se il cursore si trova in una determinata area dello schermo quando viene premuto un pulsante del mouse.  
  
 È possibile creare un'area da un rettangolo o un percorso. È anche possibile creare aree complesse combinando regioni esistenti. Il <xref:System.Drawing.Region> classe fornisce i metodi seguenti per la combinazione di regioni: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A>, e <xref:System.Drawing.Region.Complement%2A>.  
  
 L'intersezione di due aree è il set di tutti i punti appartenenti a entrambe le aree. L'unione è il set di tutti i punti appartenenti a uno o l'altro o entrambe le aree. Il complemento di un'area è il set di tutti i punti che non sono presenti nell'area. Nella figura seguente mostra l'intersezione e l'unione delle due aree illustrato nella figura precedente.  
  
 ![Aree](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.gif "AboutGdip02_Art28")  
  
 Il <xref:System.Drawing.Region.Xor%2A> metodo, applicato a una coppia di regioni, genera un'area che contiene tutti i punti che appartengono a un'area o l'altro, ma non entrambi. Il <xref:System.Drawing.Region.Exclude%2A> metodo, applicato a una coppia di regioni, genera un'area che contiene tutti i punti nella prima area che non si trovano nella seconda area. La figura seguente mostra le aree risultanti dall'applicazione di <xref:System.Drawing.Region.Xor%2A> e <xref:System.Drawing.Region.Exclude%2A> metodi alle due aree riportate all'inizio di questo argomento.  
  
 ![Aree](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.gif "AboutGdip02_Art29")  
  
 Per riempire un'area, è necessario un <xref:System.Drawing.Graphics> oggetto, un <xref:System.Drawing.Brush> , oggetto e un <xref:System.Drawing.Region> oggetto. Il <xref:System.Drawing.Graphics> oggetto fornisce il <xref:System.Drawing.Graphics.FillRegion%2A> (metodo) e <xref:System.Drawing.Brush> oggetto archivia gli attributi del riempimento, ad esempio colore o il motivo. Nell'esempio seguente inserisce un'area con un colore a tinta unita.  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Region?displayProperty=nameWithType>  
 [Linee, curve e forme](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Uso delle regioni](../../../../docs/framework/winforms/advanced/using-regions.md)
