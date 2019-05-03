---
title: 'Procedura: Enumerare i tipi di carattere installati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 92f27399cce9e03a4679c8a34fbdafcf28c32252
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004109"
---
# <a name="how-to-enumerate-installed-fonts"></a>Procedura: Enumerare i tipi di carattere installati
Il <xref:System.Drawing.Text.InstalledFontCollection> classe eredita dal <xref:System.Drawing.Text.FontCollection> classe base astratta. È possibile usare un <xref:System.Drawing.Text.InstalledFontCollection> oggetto da enumerare i tipi di carattere installati nel computer. Il <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà di un <xref:System.Drawing.Text.InstalledFontCollection> oggetto è una matrice di <xref:System.Drawing.FontFamily> oggetti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente elenca i nomi di tutte le famiglie di caratteri installate nel computer. Il codice recupera le <xref:System.Drawing.FontFamily.Name%2A> proprietà della ognuno <xref:System.Drawing.FontFamily> oggetto nella matrice restituita dal <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà. Come vengono recuperati i nomi di famiglia, questi vengono concatenati di elenco in formato delimitato da virgole. Il <xref:System.Drawing.Graphics.DrawString%2A> metodo di <xref:System.Drawing.Graphics> classe consente di disegnare l'elenco delimitato da virgole in un rettangolo.  
  
 Se si esegue il codice di esempio, l'output sarà simile a quello illustrato nella figura seguente:  
  
 ![Screenshot che mostra le famiglie di tipi di carattere installati.](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>. Inoltre, è necessario importare il <xref:System.Drawing.Text> dello spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di tipi di carattere e testo](using-fonts-and-text.md)
