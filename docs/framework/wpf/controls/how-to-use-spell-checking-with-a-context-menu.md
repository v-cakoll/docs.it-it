---
title: 'Procedura: utilizzare il controllo ortografico con un menu di scelta rapida'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 257f343a7fa01e251159797a83e89b533292b6b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a>Procedura: utilizzare il controllo ortografico con un menu di scelta rapida
Per impostazione predefinita, quando si abilita il controllo ortografico in un controllo di modifica come <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>, si ottengono le opzioni di controllo ortografico nel menu di scelta rapida. Ad esempio, quando gli utenti fare doppio clic su una parola, ricevono una serie di correzioni ortografiche suggerite o l'opzione per **Ignora tutto**. Tuttavia, quando si esegue l'override di menu di scelta rapida predefinito con un menu di scelta rapida personalizzato, questa funzionalità viene persa ed è necessario scrivere codice per riabilitare la funzionalità di controllo ortografico nel menu di scelta rapida. Nell'esempio seguente viene illustrato come abilitare questa funzionalità in un <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente il [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che crea un <xref:System.Windows.Controls.TextBox> con alcuni eventi che vengono utilizzati per implementare il menu di scelta rapida.  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato il codice che implementa il menu di scelta rapida.  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 Il codice utilizzato per raggiungere questo obiettivo con un <xref:System.Windows.Controls.RichTextBox> è simile. La differenza principale è nel passato al parametro di `GetSpellingError` metodo. Per un <xref:System.Windows.Controls.TextBox>, passare l'indice integer della posizione del punto di inserimento:  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 Per un <xref:System.Windows.Controls.RichTextBox>, passare il <xref:System.Windows.Documents.TextPointer> che specifica la posizione del cursore:  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulla classe TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [Attivare il controllo ortografico in un controllo di modifica del testo](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)  
 [Usare un menu di scelta rapida personalizzato con un oggetto TextBox](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)
