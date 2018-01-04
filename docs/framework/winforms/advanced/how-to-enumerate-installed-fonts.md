---
title: 'Procedura: enumerare i tipi di carattere installati'
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
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 905b5ecbda58d2f7edb7fc30d5505eec63a64c2b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enumerate-installed-fonts"></a>Procedura: enumerare i tipi di carattere installati
Il <xref:System.Drawing.Text.InstalledFontCollection> classe eredita la <xref:System.Drawing.Text.FontCollection> classe base astratta. È possibile utilizzare un <xref:System.Drawing.Text.InstalledFontCollection> oggetto per enumerare i tipi di carattere installati nel computer. Il <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà di un <xref:System.Drawing.Text.InstalledFontCollection> oggetto è una matrice di <xref:System.Drawing.FontFamily> oggetti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente elenca i nomi di tutte le famiglie di caratteri installate nel computer. Il codice recupera il <xref:System.Drawing.FontFamily.Name%2A> proprietà di ogni <xref:System.Drawing.FontFamily> oggetto nella matrice restituita dal <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà. Come vengono recuperati i nomi di famiglia, questi vengono concatenati all'elenco di form separati da virgola. Il <xref:System.Drawing.Graphics.DrawString%2A> metodo la <xref:System.Drawing.Graphics> classe disegna l'elenco delimitato da virgole in un rettangolo.  
  
 Se si esegue il codice di esempio, l'output sarà simile a quanto illustrato nella figura seguente.  
  
 ![Tipi di carattere installati](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Form e richiede <xref:System.Windows.Forms.PaintEventArgs> `e`, un parametro di <xref:System.Windows.Forms.PaintEventHandler>. Inoltre, è necessario importare il <xref:System.Drawing.Text> dello spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche  
 [Uso di tipi di carattere e testo](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
