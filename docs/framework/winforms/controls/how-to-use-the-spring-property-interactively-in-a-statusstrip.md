---
title: 'Procedura: Usare la proprietà Spring in modo interattivo in un controllo StatusStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
ms.openlocfilehash: a09262d2e874eebaa8c9224266f5eeb585a4f6ea
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630435"
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a>Procedura: Usare la proprietà Spring in modo interattivo in un controllo StatusStrip
È possibile usare la proprietà <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> per posizionare un controllo <xref:System.Windows.Forms.ToolStripStatusLabel> in un controllo <xref:System.Windows.Forms.StatusStrip>. La proprietà <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> determina se il controllo <xref:System.Windows.Forms.ToolStripStatusLabel> riempie automaticamente lo spazio disponibile nel controllo <xref:System.Windows.Forms.StatusStrip>.  
  
## <a name="example"></a>Esempio  
 Il seguente esempio di codice dimostra come usare la proprietà <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> per posizionare un controllo <xref:System.Windows.Forms.ToolStripStatusLabel> in un controllo <xref:System.Windows.Forms.StatusStrip>. Il gestore dell'evento <xref:System.Windows.Forms.ToolStripItem.Click> esegue un'operazione di OR esclusivo (XOR) per cambiare il valore della proprietà <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.  
  
 Per usare questo esempio di codice, compilare ed eseguire l'applicazione e quindi fare clic su **Middle (Spring)** nel <xref:System.Windows.Forms.StatusStrip> controllo per cambiare il valore della <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> proprietà.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System.Design, System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [Controllo ToolStrip](toolstrip-control-windows-forms.md)
