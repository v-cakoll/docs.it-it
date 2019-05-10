---
title: 'Procedura: Usare una matrice di colori per trasformare un singolo colore'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 9cff13cabb0cd496ee4e628664e4b92bd9e60808
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063726"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a>Procedura: Usare una matrice di colori per trasformare un singolo colore
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce il <xref:System.Drawing.Image> e <xref:System.Drawing.Bitmap> classi per l'archiviazione e la modifica delle immagini. <xref:System.Drawing.Image> e <xref:System.Drawing.Bitmap> oggetti archiviare il colore di ogni pixel come numero a 32 bit: 8 bit per ciascun rosso, verde, blu e alfa. Ognuno dei quattro componenti è un numero compreso tra 0 e 255, dove 0 rappresenta alcun intensità e 255 che rappresentano piena intensità. Il componente alfa specifica la trasparenza del colore: 0 è completamente trasparente e 255 è completamente opaco.  
  
 Un vettore di colore è una tupla con 4 del modulo (rosso, verde, blu e alfa). Ad esempio, il vettore (0, 255, 0, 255) di colore rappresenta un colore opaco che non dispone di colore rosso o blu, ma ha verde alla piena intensità.  
  
 Un'altra convenzione per la rappresentazione di colori viene utilizzato il numero 1 per piena intensità. Utilizzando questa convenzione, il colore descritto nel paragrafo precedente viene rappresentato tramite il vettore (0, 1, 0, 1). [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Usa la convenzione di 1 come piena intensità durante l'esecuzione di trasformazioni di colore.  
  
 È possibile applicare trasformazioni lineari (rotazione, ridimensionamento e simili) a vettori di colore moltiplicando i vettori di colore da una matrice 4x4. Tuttavia, non è possibile utilizzare una matrice 4x4 per eseguire una conversione (non lineare). Se si aggiunge una coordinata quinta fittizia (ad esempio, il numero 1) per ognuno dei vettori di colore, è possibile usare una matrice 5x5 applicare qualsiasi combinazione delle trasformazioni lineari e traduzioni. Una trasformazione costituita da una trasformazione lineare seguita da una traduzione viene chiamata una trasformazione affine.  
  
 Ad esempio, si supponga di che voler iniziare con il colore (0,2, 0.0, 0,4, 1.0) e applicare le trasformazioni seguenti:  
  
1. Raddoppiare la componente rossa  
  
2. Aggiungere i componenti rossi, verdi e blu 0.2  
  
 La moltiplicazione di matrici seguente eseguirà la coppia di trasformazioni nell'ordine elencato.  
  
 ![Screenshot di una matrice di trasformazione moltiplicazione.](./media/how-to-use-a-color-matrix-to-transform-a-single-color/multiplication-color-matrix.gif)
  
 Gli elementi di una matrice di colori vengono indicizzati (in base zero) dalla riga e quindi di colonna. Ad esempio, la voce nella quinta riga e alla terza colonna della matrice M è indicata da M [4] [2].  
  
 La matrice di identità di 5 × 5 (illustrato nella figura seguente) presenta 1 lungo la diagonale e 0 in qualsiasi altro. Se si moltiplica un vettore di colore per la matrice di identità, il vettore di colore rimane invariato. Un modo pratico per formare la matrice di una trasformazione di colore è iniziare con la matrice di identità e apportare una piccola modifica che produce la trasformazione desiderata.  
  
 ![Screenshot di una matrice di identità 5x5 per la trasformazione del colore.](./media/how-to-use-a-color-matrix-to-transform-a-single-color/5x5-identity-matrix-color-transformation.gif)  
  
 Per una discussione più dettagliata di matrici e le trasformazioni, vedere [sistemi di Coordinate e trasformazioni](coordinate-systems-and-transformations.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente accetta un'immagine è monocromatica (0,2, 0.0, 0,4, 1.0) e applica la trasformazione descritta nei paragrafi precedenti.  
  
 Nella figura seguente mostra l'immagine originale a sinistra e l'immagine trasformato a destra.  
  
 ![Un quadrato viola sulla sinistra e un quadrato fucsia sulla destra.](./media/how-to-use-a-color-matrix-to-transform-a-single-color/color-transformation.png)  
  
 Il codice nell'esempio seguente usa la procedura seguente per eseguire il ricolorazione:  
  
1. Inizializzare un <xref:System.Drawing.Imaging.ColorMatrix> oggetto.  
  
2. Creare un <xref:System.Drawing.Imaging.ImageAttributes> , quindi passare il <xref:System.Drawing.Imaging.ColorMatrix> dell'oggetto per il <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> metodo del <xref:System.Drawing.Imaging.ImageAttributes> oggetto.  
  
3. Passare il <xref:System.Drawing.Imaging.ImageAttributes> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro del <xref:System.Windows.Forms.Control.Paint> gestore dell'evento.  
  
## <a name="see-also"></a>Vedere anche

- [Ricolorazione di immagini](recoloring-images.md)
- [Sistemi di coordinate e trasformazioni](coordinate-systems-and-transformations.md)
