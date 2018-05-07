---
title: 'Procedura: aggiungere una filigrana a un oggetto TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: 962d6958de0811863393f930d8672769a50e8265
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a>Procedura: aggiungere una filigrana a un oggetto TextBox
Nell'esempio seguente viene illustrato come migliorare l'usabilità di un <xref:System.Windows.Controls.TextBox> visualizzando un'immagine di sfondo esplicativo all'interno del <xref:System.Windows.Controls.TextBox> fino a quando l'utente immette testo, a quel punto l'immagine viene rimossa. Inoltre, l'immagine di sfondo viene ripristinata nuovamente se l'utente rimuove l'input. Vedere la figura seguente.  
  
 ![Una casella di testo con un'immagine di sfondo](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")  
  
> [!NOTE]
>  Il motivo di un'immagine di sfondo viene utilizzata in questo esempio piuttosto che modificare semplicemente il <xref:System.Windows.Controls.TextBox.Text%2A> proprietà <xref:System.Windows.Controls.TextBox>, è che un'immagine di sfondo non interferisce con l'associazione dati.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulla classe TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Cenni preliminari sul controllo RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
