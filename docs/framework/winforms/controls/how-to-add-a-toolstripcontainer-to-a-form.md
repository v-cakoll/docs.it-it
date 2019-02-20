---
title: 'Procedura: Aggiungere un oggetto ToolStripContainer a un Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: 47279c5e8fa24accca36280f9a97200982a1451a
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "56441801"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a>Procedura: Aggiungere un oggetto ToolStripContainer a un Form
È possibile aggiungere un oggetto <xref:System.Windows.Forms.ToolStripContainer> a un Windows Form a livello di codice e quindi popolarlo con controlli.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice riportato di seguito viene illustrato come aggiungere un controllo <xref:System.Windows.Forms.ToolStripContainer> e un controllo <xref:System.Windows.Forms.ToolStrip> a un Windows Form, come aggiungere elementi al controllo <xref:System.Windows.Forms.ToolStrip> e come aggiungere il controllo <xref:System.Windows.Forms.ToolStrip> alla proprietà <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> del controllo <xref:System.Windows.Forms.ToolStripContainer>.  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System.Drawing, System.Text e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.ToolStripContainer>
- [Controllo ToolStripContainer](../../../../docs/framework/winforms/controls/toolstripcontainer-control.md)
- [Controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
