---
title: Trasformazioni globali e locali
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
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 432402fefc6c958fbab0b1450a429d9b130b8239
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="global-and-local-transformations"></a>Trasformazioni globali e locali
Una trasformazione globale è una trasformazione che si applica a ogni elemento creato da un determinato <xref:System.Drawing.Graphics> oggetto. Al contrario, una trasformazione locale è una trasformazione che si applica a un elemento specifico da disegnare.  
  
## <a name="global-transformations"></a>Trasformazioni globali  
 Per creare una trasformazione globale, costruire un <xref:System.Drawing.Graphics> e quindi modificare il relativo <xref:System.Drawing.Graphics.Transform%2A> proprietà. Il <xref:System.Drawing.Graphics.Transform%2A> proprietà è un <xref:System.Drawing.Drawing2D.Matrix> dell'oggetto, pertanto può contenere qualsiasi sequenza di trasformazioni affini. La trasformazione memorizzata nella <xref:System.Drawing.Graphics.Transform%2A> proprietà viene chiamata la trasformazione globale. Il <xref:System.Drawing.Graphics> classe fornisce numerosi metodi per la compilazione di una trasformazione complessiva composta: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, e <xref:System.Drawing.Graphics.TranslateTransform%2A>. Nell'esempio seguente disegna un'ellisse due volte: una volta prima di creare una trasformazione globale e una volta dopo. La trasformazione Ridimensiona prima di un fattore pari a 0,5 nella direzione y, quindi converte 50 unità nella direzione x e quindi ruotata di 30 gradi.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 Nella figura seguente mostra le matrici utilizzate durante la trasformazione.  
  
 ![Trasformazioni](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
>  Nell'esempio precedente, i puntini di sospensione viene ruotata intorno all'origine del sistema di coordinate, che si trova nell'angolo superiore sinistro dell'area client. Ciò produce un risultato diverso rispetto a rotazione dell'ellisse lungo il centro.  
  
## <a name="local-transformations"></a>Trasformazioni locali  
 Una trasformazione locale si applica a un elemento specifico da disegnare. Ad esempio, un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto ha un <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> metodo che consente di trasformare i dati del percorso. Nell'esempio seguente disegna un rettangolo senza alcuna trasformazione e un percorso di una trasformazione di rotazione. (Si presuppone che non sia presente alcuna trasformazione globale).  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 È possibile combinare la trasformazione globale con le trasformazioni locale per ottenere un'ampia gamma di risultati. Ad esempio, è possibile utilizzare la trasformazione globale per modificare il sistema di coordinate e trasformazioni locale per ruotare e ridimensionare gli oggetti disegnati sul nuovo sistema di coordinate.  
  
 Si supponga un sistema di coordinate con relativa origine di 200 pixel dal bordo sinistro dell'area client e 150 pixel dalla parte superiore dell'area client. Si supponga inoltre che l'unità di misura per il pixel, con l'asse x a destra e l'asse y verso l'alto. Il sistema di coordinate è l'asse y rivolta verso il basso, pertanto è necessario eseguire un riflesso tra l'asse orizzontale. Nella figura seguente viene illustrata la matrice di tale tipo di reflection.  
  
 ![Trasformazioni](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 Si supponga, quindi che è necessario eseguire una conversione di 200 unità a destra e 150 verso il basso.  
  
 Nell'esempio seguente definisce il sistema di coordinate appena descritto, impostando la trasformazione globale di un <xref:System.Drawing.Graphics> oggetto.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 Il codice seguente (inserito alla fine dell'esempio precedente) crea un percorso costituito da un singolo rettangolo con il relativo angolo inferiore sinistro all'origine del nuovo sistema di coordinate. Il rettangolo viene compilato una sola volta senza alcuna trasformazione locale e una volta con una trasformazione locale. La trasformazione locale è costituito un ridimensionamento orizzontale di un fattore pari a 2, seguito da una rotazione di 30 gradi.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 Nella figura seguente mostra il nuovo sistema di coordinate e i due rettangoli.  
  
 ![Trasformazioni](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>Vedere anche  
 [Sistemi di coordinate e trasformazioni](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [Uso di trasformazioni nel codice gestito GDI+](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
