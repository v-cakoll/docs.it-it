---
title: 'Procedura: Usare una matrice di colori per impostare i valori alfa nelle immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 79937f0801a790d4ff1ab327aaaf45ef1b881827
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199544"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>Procedura: Usare una matrice di colori per impostare i valori alfa nelle immagini
Il <xref:System.Drawing.Bitmap> classe (che eredita dal <xref:System.Drawing.Image> classe) e il <xref:System.Drawing.Imaging.ImageAttributes> classe fornisce la funzionalità per ottenere e impostare valori di pixel. È possibile usare la <xref:System.Drawing.Imaging.ImageAttributes> valori di classe per modificare il valore alfa per un'immagine intera, oppure è possibile chiamare il <xref:System.Drawing.Bitmap.SetPixel%2A> metodo il <xref:System.Drawing.Bitmap> classe per modificare i valori dei singoli pixel.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Drawing.Imaging.ImageAttributes> classe ha numerose proprietà che è possibile usare per modificare le immagini durante il rendering. Nell'esempio seguente, un <xref:System.Drawing.Imaging.ImageAttributes> oggetto viene usato per impostare tutti i valori alfa all'80% di quelle in uso. Questa operazione viene eseguita l'inizializzazione di una matrice di colori e impostando alfa ridimensionamento valore nella matrice a 0,8. L'indirizzo della matrice di colori viene passato per il <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> metodo del <xref:System.Drawing.Imaging.ImageAttributes> oggetto e il <xref:System.Drawing.Imaging.ImageAttributes> oggetto viene passato al <xref:System.Drawing.Graphics.DrawString%2A> metodo del <xref:System.Drawing.Graphics> oggetto.  
  
 Durante il rendering, i valori alfa nella mappa di bit vengono convertiti in l'80% del valore precedente. Di conseguenza un'immagine che viene fusa con lo sfondo. Come illustrato nella figura seguente, l'immagine bitmap è trasparente; è possibile visualizzare la linea nera continua attraverso di esso.  
  
 ![Utilizzo di una matrice con fusione alfa](./media/image2.png "immagine2")  
  
 In cui l'immagine sulla parte dello sfondo bianca, l'immagine è stato combinato con il colore bianco. In cui l'immagine incrocia la linea nera, l'immagine viene sfumato con il colore nero.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche

- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Linee e riempimenti con fusione alfa](alpha-blending-lines-and-fills.md)
