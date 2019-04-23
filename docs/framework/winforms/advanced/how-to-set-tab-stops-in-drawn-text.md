---
title: 'Procedura: Impostare tabulazioni nel testo disegnato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: 68dbebfc4fab773fe749f9443d0c61883099d2ab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197490"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a>Procedura: Impostare tabulazioni nel testo disegnato
È possibile impostare punti di tabulazione per il testo chiamando il <xref:System.Drawing.StringFormat.SetTabStops%2A> metodo di un <xref:System.Drawing.StringFormat> oggetto e quindi passandolo <xref:System.Drawing.StringFormat> dell'oggetto per il <xref:System.Drawing.Graphics.DrawString%2A> metodo del <xref:System.Drawing.Graphics> classe.  
  
> [!NOTE]
>  Il <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> fa uso non supporta l'aggiunta di tabulazione al testo disegnato, anche se è possibile espandere la scheda esistente viene interrotto il <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente imposta punti di tabulazione in corrispondenza di 150, 250 e 350. Quindi, il codice visualizza un elenco dei nomi e i punteggi di test.  
  
 La figura seguente mostra il testo a schede:  
  
 ![Screenshot che mostra un elenco dei nomi e i punteggi.](./media/how-to-set-tab-stops-in-drawn-text/tab-list-names-test-scores.png)  
  
 Il codice seguente passa due argomenti per il <xref:System.Drawing.StringFormat.SetTabStops%2A> (metodo). Il secondo argomento è una matrice che contiene gli offset di tabulazione. Il primo argomento passato a <xref:System.Drawing.StringFormat.SetTabStops%2A> è 0, che indica che il primo offset nella matrice vengono misurate da posizione 0, il bordo sinistro del rettangolo di delimitazione.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
  
-   L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di tipi di carattere e testo](using-fonts-and-text.md)
- [Procedura: Creare testo con GDI](how-to-draw-text-with-gdi.md)
