---
title: 'Procedura: Riempire una forma con un colore a tinta unita'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
ms.openlocfilehash: 8bc782f9496a9c1562bad2df1ba196fb39572e68
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704436"
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a>Procedura: Riempire una forma con un colore a tinta unita
Per riempire una forma con un colore a tinta unita, creare un <xref:System.Drawing.SolidBrush> dell'oggetto, quindi passarlo <xref:System.Drawing.SolidBrush> oggetto come argomento a uno dei metodi di riempimento del <xref:System.Drawing.Graphics> classe. Nell'esempio seguente viene illustrato come compilare un'ellisse con il colore rosso.  
  
## <a name="example"></a>Esempio  
 Nel codice seguente, il <xref:System.Drawing.SolidBrush.%23ctor%2A> costruttore accetta un <xref:System.Drawing.Color> oggetto come unico argomento. I valori utilizzati per il <xref:System.Drawing.Color.FromArgb%2A> metodo rappresentano i componenti alfa, rossi, verdi e blu del colore. Ognuno di questi valori deve essere compreso tra 0 e 255. I primi 255 indica che il colore è completamente opaco, e il secondo 255 indica che il componente rossa alla piena intensità. Gli due zeri indicano che i componenti verdi e blu abbiano un'intensità pari a 0.  
  
 I quattro numeri (0, 0, 100, 60) passato al <xref:System.Drawing.Graphics.FillEllipse%2A> metodo specificare il percorso e le dimensioni del rettangolo di delimitazione dell'ellisse. Il rettangolo dispone di un angolo superiore sinistro del (0, 0), la larghezza è pari a 100 e altezza pari a 60.  
  
 [!code-csharp[System.Drawing.UsingABrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro del gestore eventi <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>Vedere anche
- [Uso di un oggetto Brush per il riempimento di forme](using-a-brush-to-fill-shapes.md)
