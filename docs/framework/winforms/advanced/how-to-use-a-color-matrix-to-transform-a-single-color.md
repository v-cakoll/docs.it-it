---
title: 'Procedura: Usare una matrice di colori per trasformare un singolo colore'
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
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 60da29b60d2b9b5b98c76a0a9c3ae73ac9142bbd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a>Procedura: Usare una matrice di colori per trasformare un singolo colore
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]fornisce il <xref:System.Drawing.Image> e <xref:System.Drawing.Bitmap> classi per l'archiviazione e la modifica di immagini. <xref:System.Drawing.Image>e <xref:System.Drawing.Bitmap> oggetti archiviano il colore di ciascun pixel come numero a 32 bit: 8 bit ogni per rosso, verde, blu e alfa. Ognuno dei quattro componenti è un numero compreso tra 0 e 255, dove 0 rappresenta nessun intensità e 255 che rappresenta intensità completo. Il componente alfa specifica la trasparenza del colore: 0 è completamente trasparente e 255 è completamente opaco.  
  
 Un vettore di colore è una tupla con 4 del modulo (rosso, verde, blu e alfa). Ad esempio, il vettore (0, 255, 0, 255) di colore rappresenta un colore opaco che non ha rosso o blu, ma è verde intensità completo.  
  
 Un'altra convenzione per la rappresentazione di colori utilizza il numero 1 per intensità completo. Utilizzando questa convenzione, il colore descritto nel paragrafo precedente viene rappresentato tramite il vettore (0, 1, 0, 1). [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]utilizza la convenzione di 1 come intensità completo quando si eseguono trasformazioni di colore.  
  
 È possibile applicare trasformazioni lineari (rotazione, ridimensionamento e così via) a vettori di colore moltiplicando i vettori di colore per una matrice 4x4. Tuttavia, è possibile utilizzare una matrice 4x4 per eseguire una conversione (non lineare). Se si aggiunge una quinta coordinata finta (ad esempio, il numero 1) per ognuno dei vettori di colore, è possibile utilizzare una matrice di 5 × 5 per applicare qualsiasi combinazione di trasformazioni lineari e traduzioni. Una trasformazione costituita da una trasformazione lineare seguita da una traduzione è definita una trasformazione affine.  
  
 Si supponga, ad esempio, che si desidera iniziare con il colore (0,2, 0,0, 0,4, 1.0) e applicare le trasformazioni seguenti:  
  
1.  Raddoppiare il componente rosso  
  
2.  Aggiungere 0,2 ai componenti rossi, verde e blu  
  
 Moltiplicazione seguente eseguirà la coppia di trasformazioni nell'ordine elencato.  
  
 ![Nuova colorazione](../../../../docs/framework/winforms/advanced/media/recoloring01.gif "recoloring01")  
  
 Gli elementi di una matrice di colori vengono indicizzati (in base zero) da righe e quindi colonne. Ad esempio, la voce nella quinta riga e nella terza colonna della matrice M è identificata da M [4] [2].  
  
 La matrice di identità di 5 × 5 (mostrato nella figura seguente), 1 sulla diagonale e 0 in qualsiasi altro. Se si moltiplica un vettore di colore per la matrice di identità, il vettore di colore rimane invariato. Un modo pratico per formare la matrice di trasformazione di colore è iniziare con la matrice di identità e apportare una piccola modifica che produce la trasformazione desiderata.  
  
 ![Nuova colorazione](../../../../docs/framework/winforms/advanced/media/recoloring02.gif "recoloring02")  
  
 Per informazioni dettagliate sulle matrici e le trasformazioni, vedere [sistemi di Coordinate e trasformazioni](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente accetta un'immagine è monocromatica (0,2, 0,0, 0,4, 1.0) e si applica la trasformazione descritta nei paragrafi precedenti.  
  
 Nella figura seguente mostra l'immagine originale a sinistra e l'immagine trasformato a destra.  
  
 ![Colori](../../../../docs/framework/winforms/advanced/media/colortrans1.png "colortrans1")  
  
 Il codice nell'esempio seguente usa la procedura seguente per la ricolorazione:  
  
1.  Inizializzare un <xref:System.Drawing.Imaging.ColorMatrix> oggetto.  
  
2.  Creare un <xref:System.Drawing.Imaging.ImageAttributes> , quindi passare il <xref:System.Drawing.Imaging.ColorMatrix> dell'oggetto per il <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> metodo il <xref:System.Drawing.Imaging.ImageAttributes> oggetto.  
  
3.  Passare il <xref:System.Drawing.Imaging.ImageAttributes> dell'oggetto per il <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche  
 [Ricolorazione di immagini](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [Sistemi di coordinate e trasformazioni](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)
