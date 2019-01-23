---
title: 'Procedura: Creare un controllo TextBox a più righe'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: ca1b499b2acdfd9fd2ff0f57f2b0c07d7da10789
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517825"
---
# <a name="how-to-create-a-multiline-textbox-control"></a>Procedura: Creare un controllo TextBox a più righe
In questo esempio viene illustrato come utilizzare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per definire un <xref:System.Windows.Controls.TextBox> controllo che si espanderà automaticamente per inserire più righe di testo.  
  
## <a name="example"></a>Esempio  
 Impostando il <xref:System.Windows.Controls.TextBox.TextWrapping%2A> dell'attributo **eseguire il wrapping** causerà il testo immesso eseguire il wrapping in una nuova riga quando il bordo del <xref:System.Windows.Controls.TextBox> controllo viene raggiunto, si espande automaticamente il <xref:System.Windows.Controls.TextBox> controllo per includere una nuova riga, se necessario.  
  
 Impostando il <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> dell'attributo **true** fa sì che una nuova riga deve essere inserito quando viene premuto il tasto INVIO, espande automaticamente il <xref:System.Windows.Controls.TextBox> per inserire una nuova riga, se necessario.  
  
 Il <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attributo aggiunge una barra di scorrimento per il <xref:System.Windows.Controls.TextBox>, in modo che il contenuto del <xref:System.Windows.Controls.TextBox> se è possibile scorrere il <xref:System.Windows.Controls.TextBox> espande oltre la dimensione della cornice o finestra che lo racchiude.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.TextWrapping>
- [Cenni preliminari sulla classe TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
