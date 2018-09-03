---
title: 'Procedura: creare un controllo ToolStrip professionale'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
ms.openlocfilehash: 10799ad4db103fb50a25e600418fb8b5003c24ea
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486056"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a>Procedura: creare un controllo ToolStrip professionale
Per assegnare un aspetto professionale ai controlli <xref:System.Windows.Forms.ToolStrip> dell'applicazione è possibile scrivere una classe personalizzata derivata dal tipo <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.  
  
 È disponibile supporto completo per questa funzionalità in Visual Studio.  
  
 Vedere [Procedura dettagliata: creazione di un controllo ToolStrip professionale](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md).  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come utilizzare <xref:System.Windows.Forms.ToolStrip> controlli per creare un controllo composito che imita la **riquadro di spostamento** fornito da Microsoft® Outlook®.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  Vedere anche [Procedura dettagliata: creazione di un controllo ToolStrip professionale](walkthrough-creating-a-professionally-styled-toolstrip-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [Controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [Procedura: Specificare voci di menu standard in un form](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)
