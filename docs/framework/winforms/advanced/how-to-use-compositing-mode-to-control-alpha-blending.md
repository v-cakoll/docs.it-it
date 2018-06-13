---
title: 'Procedura: utilizzare la modalità di composizione per controllare la fusione alfa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 55c6db1029c6823652ac29fca46f6f8dc4ec40d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527002"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a>Procedura: utilizzare la modalità di composizione per controllare la fusione alfa
Può accadere quando si desidera creare una bitmap fuori schermo che presenta le caratteristiche seguenti:  
  
-   Colori hanno valori alfa minore di 255.  
  
-   I colori non sono alfa combinati tra loro durante la creazione di bitmap.  
  
-   Quando si visualizza l'immagine bitmap completata, i colori nella mappa di bit sono alpha sfumato con i colori di sfondo sul dispositivo di visualizzazione.  
  
 Per creare una mappa di bit, creare uno spazio vuoto <xref:System.Drawing.Bitmap> dell'oggetto e quindi creare un <xref:System.Drawing.Graphics> oggetto basato sull'immagine. Impostare la modalità di composizione del <xref:System.Drawing.Graphics> oggetto <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un <xref:System.Drawing.Graphics> oggetto basato su un <xref:System.Drawing.Bitmap> oggetto. Il codice Usa il <xref:System.Drawing.Graphics> oggetto insieme a due pennelli semitrasparenti (alfa = 160) per colorare l'immagine bitmap. Il codice verrà inserito un'ellisse rossa e un'ellisse verde mediante i pennelli semitrasparenti. Ellisse di colore verde si sovrappone colore rosso, ma il verde non viene sfumato con il rosso perché la modalità di composizione del <xref:System.Drawing.Graphics> oggetto è impostato su <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.  
  
 Il codice la bitmap disegnata sullo schermo due volte: una volta su sfondo bianco e una volta su uno sfondo. Il pixel della bitmap che fanno parte di due ellissi presentano un componente alfa di 160, pertanto i puntini di sospensione sono combinati con i colori di sfondo sullo schermo.  
  
 Nella figura seguente mostra l'output dell'esempio di codice. Si noti che i puntini di sospensione sono combinati con lo sfondo, ma non sono combinati tra loro.  
  
 ![Copia di origine](../../../../docs/framework/winforms/advanced/media/sourcecopy.png "sourcecopy")  
  
 L'esempio di codice contiene questa istruzione:  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 Se si desidera i puntini di sospensione per essere combinati tra loro e con lo sfondo, è possibile modificare l'istruzione per le operazioni seguenti:  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 Nella figura seguente mostra l'output del codice modificato.  
  
 ![Origine su](../../../../docs/framework/winforms/advanced/media/sourceover.png "sourceover")  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Drawing.Color.FromArgb%2A>  
 [Linee e riempimenti con fusione alfa](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
