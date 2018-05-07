---
title: 'Procedura: creare un controllo TextBox su più righe'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 9f4c9e637b686c82b4ec8a4a5d6d3a78d46f97c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-multiline-textbox-control"></a>Procedura: creare un controllo TextBox su più righe
In questo esempio viene illustrato come utilizzare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per definire un <xref:System.Windows.Controls.TextBox> controllo che si espanderà automaticamente per inserire più righe di testo.  
  
## <a name="example"></a>Esempio  
 Impostazione di <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attributo **eseguire il wrapping** il testo immesso eseguire il wrapping in una nuova riga quando il bordo del <xref:System.Windows.Controls.TextBox> controllo viene raggiunto, si espande automaticamente il <xref:System.Windows.Controls.TextBox> controllo per inserire una nuova riga, se necessario.  
  
 L'impostazione di <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attributo **true** una nuova riga da inserire quando viene premuto il tasto INVIO, espande automaticamente il <xref:System.Windows.Controls.TextBox> per inserire una nuova riga, se necessario.  
  
 Il <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attributo aggiunge una barra di scorrimento di <xref:System.Windows.Controls.TextBox>, in modo che il contenuto del <xref:System.Windows.Controls.TextBox> se è possibile scorrere il <xref:System.Windows.Controls.TextBox> si espanda oltre il frame o la finestra che lo contiene.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.TextWrapping>  
 [Cenni preliminari sulla classe TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
