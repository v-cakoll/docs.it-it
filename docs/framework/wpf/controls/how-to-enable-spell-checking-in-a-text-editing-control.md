---
title: 'Procedura: Attivare il controllo ortografico in un controllo di modifica del testo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- spellchecking [WPF]
- real-time spellchecking
- TextBox control [WPF], real-time spellchecking
- spelling checker [WPF]
- checking spelling [WPF]
ms.assetid: 6f953d2b-67e8-4012-84ce-53c0e958da47
ms.openlocfilehash: 7381bafc349506d89058581e9ed62a4348a72865
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076848"
---
# <a name="how-to-enable-spell-checking-in-a-text-editing-control"></a>Procedura: Attivare il controllo ortografico in un controllo di modifica del testo
Nell'esempio seguente viene illustrato come abilitare controllo ortografico in tempo reale in un <xref:System.Windows.Controls.TextBox> usando il <xref:System.Windows.Controls.SpellCheck.IsEnabled%2A> proprietà del <xref:System.Windows.Controls.SpellCheck> classe.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellCheckExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/spellcheckexample.xaml#spellcheckexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_procedural_snip#SpellCheckCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_procedural_snip/CSharp/SpellCheckExample.cs#spellcheckcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_procedural_snip#SpellCheckCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_procedural_snip/visualbasic/spellcheckexample.vb#spellcheckcodeexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Usare il controllo ortografico con un menu di scelta rapida](how-to-use-spell-checking-with-a-context-menu.md)
- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni preliminari sul controllo RichTextBox](richtextbox-overview.md)
