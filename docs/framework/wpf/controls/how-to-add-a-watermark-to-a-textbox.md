---
title: 'Procedura: Aggiungere una filigrana a un oggetto TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: ef2536f03ba6ed08e27d2fcf30cd1f72df2cf460
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142415"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a>Procedura: Aggiungere una filigrana a un oggetto TextBox
Nell'esempio seguente viene illustrato come migliorare l'usabilità di un <xref:System.Windows.Controls.TextBox> visualizzando un'immagine di sfondo esplicativo all'interno del <xref:System.Windows.Controls.TextBox> fino a quando l'utente immette testo, a quel punto l'immagine viene rimossa. Inoltre, l'immagine di sfondo viene ripristinata nuovamente se l'utente rimuove l'input. Vedere la figura seguente.  
  
 ![Una casella di testo con un'immagine di sfondo](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")  
  
> [!NOTE]
>  Il motivo per un'immagine di sfondo viene usata in questo esempio piuttosto che modificare semplicemente la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà di <xref:System.Windows.Controls.TextBox>, è che un'immagine di sfondo non interferisce con il data binding.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
