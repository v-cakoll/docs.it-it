---
title: 'Procedura: impostare punti di tabulazione nel testo disegnato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: e7f3fe9757db26bcc9dc9735f3d3d854edb7c099
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Procedura: impostare punti di tabulazione nel testo disegnato
È possibile impostare punti di tabulazione per il testo chiamando il <xref:System.Drawing.StringFormat.SetTabStops%2A> metodo di un <xref:System.Drawing.StringFormat> oggetto e quindi passando il <xref:System.Drawing.StringFormat> dell'oggetto per il <xref:System.Drawing.Graphics.DrawString%2A> metodo la <xref:System.Drawing.Graphics> classe.  
  
> [!NOTE]
>  Il <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> fa uso non supporta l'aggiunta di punti di tabulazione al testo disegnato, sebbene sia possibile espandere una scheda esistente viene interrotto il <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente imposta punti di tabulazione in corrispondenza di 150, 250 e 350. Quindi, il codice visualizza un elenco dei nomi e i punteggi di test.  
  
 Nella figura seguente mostra il testo a schede.  
  
 ![Testo caratteri](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")  
  
 Il codice seguente passa due argomenti per il <xref:System.Drawing.StringFormat.SetTabStops%2A> metodo. Il secondo argomento è una matrice che contiene gli offset di tabulazione. Il primo argomento passato a <xref:System.Drawing.StringFormat.SetTabStops%2A> è 0, che indica che il primo offset nella matrice viene misurato dalla posizione 0, il bordo sinistro del rettangolo di delimitazione.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di tipi di carattere e testo](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Procedura: Creare testo con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
