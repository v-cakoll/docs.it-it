---
title: 'Procedura: Disegnare linee opache e semitrasparenti'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- transparency [Windows Forms], lines
- lines [Windows Forms], drawing alpha blended
- alpha blending [Windows Forms], drawing lines
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
ms.openlocfilehash: 7408722dc13e83828cfca3f0615a2730e3c53461
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004029"
---
# <a name="how-to-draw-opaque-and-semitransparent-lines"></a>Procedura: Disegnare linee opache e semitrasparenti
Quando si disegna una linea, è necessario passare un oggetto <xref:System.Drawing.Pen> al metodo <xref:System.Drawing.Graphics.DrawLine%2A> della classe <xref:System.Drawing.Graphics>. Uno dei parametri del costruttore <xref:System.Drawing.Pen.%23ctor%2A> è un oggetto <xref:System.Drawing.Color>. Per disegnare una linea opaca, impostare il componente alfa del colore su 255. Per disegnare una linea semitrasparente, impostare il componente alfa su un valore qualsiasi compreso tra 1 e 254.  
  
 Quando si disegna una linea semitrasparente su uno sfondo, il colore della linea viene sfumato con i colori dello sfondo. Il componente alfa specifica come si combinano i colori della linea e dello sfondo. I valori alfa vicini a 0 rendono più intensi i colori di sfondo, mentre i valori alfa più vicini a 255 rendono più intenso il colore della linea.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente disegna un'immagine bitmap e quindi tre linee che usano la stessa bitmap come sfondo. Per la prima linea si usa un componente alfa con un valore pari a 255, quindi la linea risulta opaca. Per la seconda e la terza linea si usa un componente alfa con un valore pari a 128, quindi le linee risultano semitrasparenti. L'immagine di sfondo è visibile attraverso le linee. L'istruzione che imposta la proprietà <xref:System.Drawing.Graphics.CompositingQuality%2A> determina la sfumatura della terza riga ottenuta in combinazione con la correzione gamma.  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
 Nella figura seguente mostra l'output del codice seguente:  
  
 ![Figura che mostra l'output opache e semitrasparenti](./media/how-to-draw-opaque-and-semitransparent-lines/opaque-semitransparent-lines.png)  

## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche

- [Linee e riempimenti con fusione alfa](alpha-blending-lines-and-fills.md)
- [Procedura: Assegnare al controllo uno sfondo trasparente](../controls/how-to-give-your-control-a-transparent-background.md)
- [Procedura: Disegnare con pennelli opachi e semitrasparenti](how-to-draw-with-opaque-and-semitransparent-brushes.md)
