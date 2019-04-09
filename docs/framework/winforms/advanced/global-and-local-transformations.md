---
title: Trasformazioni globali e locali
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- matrices [Windows Forms], using transformations
- transformations [Windows Forms], global
- transformations [Windows Forms], local
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
ms.openlocfilehash: e4ed103e781cc2e59d62c11f3233357c77b81cb9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213753"
---
# <a name="global-and-local-transformations"></a>Trasformazioni globali e locali
Una trasformazione globale è una trasformazione che si applica a ogni elemento tracciata da un determinato <xref:System.Drawing.Graphics> oggetto. Al contrario, una trasformazione locale è una trasformazione che si applica a un elemento specifico da disegnare.  
  
## <a name="global-transformations"></a>Trasformazioni globali  
 Per creare una trasformazione globale, creare un <xref:System.Drawing.Graphics> dell'oggetto e quindi modificare i relativi <xref:System.Drawing.Graphics.Transform%2A> proprietà. Il <xref:System.Drawing.Graphics.Transform%2A> proprietà è un <xref:System.Drawing.Drawing2D.Matrix> dell'oggetto, pertanto può contenere qualsiasi sequenza di trasformazioni affini. La trasformazione archiviati nel <xref:System.Drawing.Graphics.Transform%2A> proprietà viene chiamata la trasformazione globale. Il <xref:System.Drawing.Graphics> classe fornisce diversi metodi per la creazione di una trasformazione globale composito: <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A>, e <xref:System.Drawing.Graphics.TranslateTransform%2A>. L'esempio seguente disegna un'ellisse due volte: una volta prima di creare una trasformazione globale e una volta dopo. La trasformazione prima di tutto ridimensiona in base un fattore pari a 0,5 nella direzione y, quindi si traduce nella direzione x 50 unità e quindi Ruota di 30 gradi.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 La figura seguente mostra le matrici coinvolti nella trasformazione.  
  
 ![Transformations](./media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
>  Nell'esempio precedente, i puntini di sospensione viene ruotato intorno all'origine del sistema di coordinate, che è nell'angolo superiore sinistro dell'area client. Ciò produce un risultato diverso rispetto a rotazione dell'ellisse intorno al proprio centro.  
  
## <a name="local-transformations"></a>Trasformazioni locale  
 Si applica una trasformazione locale a un elemento specifico da disegnare. Ad esempio, un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto ha un <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> metodo che consente di trasformare i punti dati del percorso. Nell'esempio seguente disegna un rettangolo senza alcuna trasformazione e un percorso con una trasformazione di rotazione. (Si supponga che non vi sia alcuna trasformazione globale).  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 È possibile combinare la trasformazione globale con le trasformazioni locale per ottenere un'ampia gamma di risultati. Ad esempio, è possibile utilizzare la trasformazione globale per rivedere il sistema di coordinate e trasformazioni locale per ruotare e ridimensionare gli oggetti disegnati sul nuovo sistema di coordinate.  
  
 Si supponga di che voler un sistema di coordinate con relativa origine di 200 pixel dal bordo sinistro dell'area client e 150 pixel dalla parte superiore dell'area client. Inoltre, presuppongono che si desidera che l'unità di misura a essere il pixel, con l'asse x che punta a destra e l'asse y verso l'alto. Il sistema di coordinate predefinito ha l'asse y rivolta verso il basso, quindi è necessario eseguire una reflection sull'asse orizzontale. Nella figura seguente viene illustrata la matrice di questo tipo una reflection.  
  
 ![Transformations](./media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 Si supponga, quindi che è necessario eseguire una conversione di 200 unità a destra e 150 unità verso il basso.  
  
 L'esempio seguente stabilisce il sistema di coordinate appena descritto, impostando la trasformazione globale di un <xref:System.Drawing.Graphics> oggetto.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 Il codice seguente (inserito alla fine dell'esempio precedente) crea un percorso che è costituito da un rettangolo singolo con relativo angolo inferiore sinistro in corrispondenza dell'origine del nuovo sistema di coordinate. Il rettangolo viene riempito una sola volta senza alcuna trasformazione locale e una volta con una trasformazione locale. La trasformazione locale costituita da una scalabilità orizzontale di un fattore pari a 2 seguita da una rotazione di 30 gradi.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 La figura seguente mostra il nuovo sistema di coordinate e i due rettangoli.  
  
 ![Transformations](./media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>Vedere anche

- [Sistemi di coordinate e trasformazioni](coordinate-systems-and-transformations.md)
- [Utilizzo di trasformazioni nel codice gestito GDI+](using-transformations-in-managed-gdi.md)
