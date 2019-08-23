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
ms.openlocfilehash: f62efb31e95b0797272997fadbc28459579a0de0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955195"
---
# <a name="global-and-local-transformations"></a>Trasformazioni globali e locali
Una trasformazione globale è una trasformazione che viene applicata a ogni elemento disegnato da un <xref:System.Drawing.Graphics> determinato oggetto. Una trasformazione locale è invece una trasformazione che si applica a un elemento specifico da disegnare.  
  
## <a name="global-transformations"></a>Trasformazioni globali  
 Per creare una trasformazione globale, costruire un <xref:System.Drawing.Graphics> oggetto e quindi modificarne la <xref:System.Drawing.Graphics.Transform%2A> proprietà. La <xref:System.Drawing.Graphics.Transform%2A> proprietà è un <xref:System.Drawing.Drawing2D.Matrix> oggetto, in modo che possa conservare qualsiasi sequenza di trasformazioni affini. La trasformazione archiviata nella <xref:System.Drawing.Graphics.Transform%2A> proprietà viene chiamata trasformazione globale. La <xref:System.Drawing.Graphics> classe fornisce diversi metodi per la creazione di una trasformazione globale composita <xref:System.Drawing.Graphics.RotateTransform%2A>: <xref:System.Drawing.Graphics.ScaleTransform%2A> <xref:System.Drawing.Graphics.MultiplyTransform%2A>,, <xref:System.Drawing.Graphics.TranslateTransform%2A>e. Nell'esempio seguente viene disegnata un'ellisse due volte: una volta prima di creare una trasformazione globale e una volta dopo. La trasformazione viene innanzitutto ridimensionata in base a un fattore di 0,5 nella direzione y, quindi converte 50 unità nella direzione x e quindi ruota di 30 gradi.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 Nella figura seguente sono illustrate le matrici incluse nella trasformazione.  
  
 ![] Trasformazioni (./media/aboutgdip05-art14.gif "AboutGdip05_art14")  
  
> [!NOTE]
> Nell'esempio precedente, l'ellisse viene ruotata sull'origine del sistema di coordinate, che si trova nell'angolo superiore sinistro dell'area client. Questo produce un risultato diverso rispetto alla rotazione dell'ellisse sul proprio centro.  
  
## <a name="local-transformations"></a>Trasformazioni locali  
 Una trasformazione locale si applica a un elemento specifico da disegnare. Un <xref:System.Drawing.Drawing2D.GraphicsPath> oggetto, ad esempio, dispone <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> di un metodo che consente di trasformare i punti dati di tale percorso. Nell'esempio seguente viene disegnato un rettangolo senza trasformazione e un percorso con una trasformazione di rotazione. (Si supponga che non esista alcuna trasformazione globale).  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 È possibile combinare la trasformazione globale con le trasformazioni locali per ottenere una serie di risultati. È ad esempio possibile utilizzare la trasformazione mondo per modificare il sistema di coordinate e utilizzare le trasformazioni locali per ruotare e ridimensionare gli oggetti disegnati nel nuovo sistema di coordinate.  
  
 Si supponga di volere un sistema di coordinate con origine 200 pixel dal bordo sinistro dell'area client e 150 pixel dalla parte superiore dell'area client. Si supponga inoltre che l'unità di misura sia il pixel, con l'asse x che punta verso destra e l'asse y che punta verso l'alto. Il sistema di coordinate predefinito ha l'asse y che punta verso il basso ed è quindi necessario eseguire una reflection sull'asse orizzontale. Nella figura seguente viene illustrata la matrice di tale Reflection.  
  
 ![] Trasformazioni (./media/aboutgdip05-art15.gif "AboutGdip05_art15")  
  
 Si supponga quindi che sia necessario eseguire una traduzione 200 unità a destra e 150 unità in basso.  
  
 Nell'esempio seguente viene stabilito il sistema di coordinate appena descritto impostando la trasformazione globale <xref:System.Drawing.Graphics> di un oggetto.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 Il codice seguente (inserito alla fine dell'esempio precedente) crea un percorso costituito da un singolo rettangolo con l'angolo inferiore sinistro all'origine del nuovo sistema di coordinate. Il rettangolo viene compilato una volta senza alcuna trasformazione locale e una volta con una trasformazione locale. La trasformazione locale è costituita da un ridimensionamento orizzontale di un fattore 2 seguito da una rotazione di 30 gradi.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 Nella figura seguente vengono illustrati il nuovo sistema di coordinate e i due rettangoli.  
  
 ![] Trasformazioni (./media/aboutgdip05-art16.gif "AboutGdip05_art16")  
  
## <a name="see-also"></a>Vedere anche

- [Sistemi di coordinate e trasformazioni](coordinate-systems-and-transformations.md)
- [Uso di trasformazioni nel codice gestito GDI+](using-transformations-in-managed-gdi.md)
