---
title: 'Procedura: impostare lo stato attivo in un controllo TextBox'
description: Informazioni su come usare il metodo Focus per impostare lo stato attivo su un controllo TextBox Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
ms.openlocfilehash: e107c22a3c5b701e02cbc8506d10fa35ee15c79d
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168055"
---
# <a name="how-to-set-focus-in-a-textbox-control"></a>Procedura: impostare lo stato attivo in un controllo TextBox
Questo esempio illustra come usare il <xref:System.Windows.UIElement.Focus%2A> metodo per impostare lo stato attivo su un <xref:System.Windows.Controls.TextBox> controllo.  
  
## <a name="example"></a>Esempio  
 Nell' [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] esempio seguente viene descritto un semplice <xref:System.Windows.Controls.TextBox> controllo denominato *tbFocusMe*  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene chiamato il <xref:System.Windows.UIElement.Focus%2A> metodo per impostare lo stato attivo sul <xref:System.Windows.Controls.TextBox> controllo con il nome *tbFocusMe*.  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.UIElement.Focusable%2A>
- <xref:System.Windows.UIElement.IsFocused%2A>
- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
