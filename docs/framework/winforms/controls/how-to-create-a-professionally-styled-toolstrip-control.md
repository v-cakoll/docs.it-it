---
title: 'Procedura: Creare un controllo ToolStrip professionale'
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
ms.openlocfilehash: 6da6e113867efed79dfcd02f3b89ee1f9ae13c4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746667"
---
# <a name="how-to-create-a-professionally-styled-toolstrip-control"></a>Procedura: Creare un controllo ToolStrip professionale
Per assegnare un aspetto professionale ai controlli <xref:System.Windows.Forms.ToolStrip> dell'applicazione è possibile scrivere una classe personalizzata derivata dal tipo <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.  
  
 È disponibile supporto completo per questa funzionalità in Visual Studio.  
  
 Vedere [Procedura dettagliata: Creazione di un controllo ToolStrip professionale](walkthrough-creating-a-professionally-styled-toolstrip-control.md).  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come utilizzare <xref:System.Windows.Forms.ToolStrip> controlli per creare un controllo composito che imita la **riquadro di spostamento** fornito da Microsoft® Outlook®.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System.Drawing e System.Windows.Forms.  
  
 Per informazioni sulla compilazione di questo esempio dalla riga di comando per Visual Basic o Visual c#, vedere [compilazione dalla riga di comando](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oppure [con la creazione della riga di comando csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). È anche possibile compilare questo esempio in Visual Studio incollando il codice in un nuovo progetto.  Vedere anche [procedura dettagliata: Creazione di un controllo ToolStrip professionale](walkthrough-creating-a-professionally-styled-toolstrip-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [Controllo ToolStrip](toolstrip-control-windows-forms.md)
- [Procedura: Specificare voci di Menu Standard in un Form](how-to-provide-standard-menu-items-to-a-form.md)
