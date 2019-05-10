---
title: 'Procedura: Usare la modalità di composizione per controllare la fusione alfa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: ad9437d9c250f067f26f61638b66fbc30fa3b599
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623922"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a>Procedura: Usare la modalità di composizione per controllare la fusione alfa
Può accadere quando si desidera creare una bitmap fuori schermo che presenta le caratteristiche seguenti:  
  
- Colori abbiano valori alfa minore di 255.  
  
- I colori non sono alfa combinati tra loro quando si crea la bitmap.  
  
- Quando si visualizza l'immagine bitmap completata, i colori nella mappa di bit sono alfa sfumata con i colori di sfondo sul dispositivo di visualizzazione.  
  
 Per creare una mappa di bit, costruire un valore vuoto <xref:System.Drawing.Bitmap> dell'oggetto e quindi costruire un <xref:System.Drawing.Graphics> oggetto basato sull'immagine. Impostare la modalità di composizione del <xref:System.Drawing.Graphics> oggetto <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea una <xref:System.Drawing.Graphics> oggetto basato su un <xref:System.Drawing.Bitmap> oggetto. Il codice Usa il <xref:System.Drawing.Graphics> oggetto insieme ai due pennelli semitrasparenti (alpha = 160) per disegnare sulla bitmap. Il codice viene compilato un'ellisse rossa e un'ellisse verde usando i pennelli semitrasparenti. Ellisse di colore verde si sovrappone a rosso puntini di sospensione, ma verde non viene sfumato con il colore rosso perché la modalità di composizione del <xref:System.Drawing.Graphics> è impostata su <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy>.  
  
 Il codice consente di disegnare la bitmap nella schermata di due volte: una volta su sfondo bianco e una volta su uno sfondo. I pixel nella bitmap che fanno parte di due ellissi dispone di un componente alfa pari a 160, pertanto i puntini di sospensione vengono combinati con i colori di sfondo sullo schermo.  
  
 Nella figura seguente mostra l'output dell'esempio di codice. Si noti che i puntini di sospensione vengono combinati con lo sfondo, ma non devono essere smussati tra loro.  
  
 ![Diagramma che mostra ellissi sfumato con lo sfondo, non tra loro.](./media/how-to-use-compositing-mode-to-control-alpha-blending/ellipses-blended-background.png)  
  
 L'esempio di codice contiene l'istruzione seguente:  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 Se si desidera che i puntini di sospensione per essere combinati tra loro e con lo sfondo, è possibile modificare tale istruzione come segue:  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 Nella figura seguente mostra l'output del codice modificato.  
  
 ![Diagramma che mostra i puntini di sospensione combinati tra loro e con lo sfondo.](./media/how-to-use-compositing-mode-to-control-alpha-blending/blend-ellipses-background.png)  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs>`e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Color.FromArgb%2A>
- [Linee e riempimenti con fusione alfa](alpha-blending-lines-and-fills.md)
