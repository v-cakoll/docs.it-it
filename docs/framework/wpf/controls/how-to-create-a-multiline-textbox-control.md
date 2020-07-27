---
title: 'Procedura: creare un controllo TextBox su più righe'
description: Informazioni su come utilizzare XAML per definire un controllo TextBox che si espande in modo da includere più righe di testo in un'applicazione Windows Presentation Foundation.
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 0a88d4d768884df135afddb491431650b9ba2d24
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166246"
---
# <a name="how-to-create-a-multiline-textbox-control"></a>Procedura: creare un controllo TextBox su più righe
Questo esempio illustra come usare [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per definire un <xref:System.Windows.Controls.TextBox> controllo che si espanderà automaticamente per contenere più righe di testo.  
  
## <a name="example"></a>Esempio  
 Se si imposta l' <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attributo su **Wrap** , il testo immesso verrà sottoposto a wrapping in una nuova riga quando viene raggiunto il bordo del <xref:System.Windows.Controls.TextBox> controllo, espandendo automaticamente il <xref:System.Windows.Controls.TextBox> controllo in modo da includere una nuova riga, se necessario.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A>Se si imposta l'attributo su **true** , viene inserita una nuova riga quando viene premuto il tasto restituito, una volta che viene nuovamente espansa automaticamente <xref:System.Windows.Controls.TextBox> per includere la stanza per una nuova riga, se necessario.  
  
 L' <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attributo aggiunge una barra di scorrimento a <xref:System.Windows.Controls.TextBox> , in modo che sia possibile scorrere il contenuto di <xref:System.Windows.Controls.TextBox> se l'oggetto <xref:System.Windows.Controls.TextBox> si espande oltre le dimensioni del frame o della finestra che lo racchiude.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.TextWrapping>
- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
