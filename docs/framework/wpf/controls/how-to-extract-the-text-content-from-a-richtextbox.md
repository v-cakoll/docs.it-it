---
title: 'Procedura: estrarre il contenuto di testo da un oggetto RichTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: 309fe15c76c17a79e11341f3a50c0bf5a7a2cc21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553936"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a>Procedura: estrarre il contenuto di testo da un oggetto RichTextBox
In questo esempio viene illustrato come estrarre il contenuto di un <xref:System.Windows.Controls.RichTextBox> come testo normale.  
  
## <a name="example"></a>Esempio  
 Nell'esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] codice descrive un oggetto denominato <xref:System.Windows.Controls.RichTextBox> controllo con contenuto semplice.  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente implementa un metodo che accetta un <xref:System.Windows.Controls.RichTextBox> come argomento e restituisce una stringa che rappresenta il contenuto di testo normale di <xref:System.Windows.Controls.RichTextBox>.  
  
 Il metodo crea un nuovo <xref:System.Windows.Documents.TextRange> dal contenuto del <xref:System.Windows.Controls.RichTextBox>, usando il <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> e <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> per indicare l'intervallo di contenuti da estrarre.  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> e <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> ogni restituiscono una <xref:System.Windows.Documents.TextPointer>e siano accessibili in FlowDocument sottostante che rappresenta il contenuto del <xref:System.Windows.Controls.RichTextBox>.  <xref:System.Windows.Documents.TextRange> fornisce una proprietà di testo, che restituisce le parti di testo normale il <xref:System.Windows.Documents.TextRange> sotto forma di stringa.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [Cenni preliminari sulla classe TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
