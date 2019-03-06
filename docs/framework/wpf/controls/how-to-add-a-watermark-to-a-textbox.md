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
ms.openlocfilehash: 5a2b48c6f580def98a47913c4909d0c57aca0974
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359420"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="63a51-102">Procedura: Aggiungere una filigrana a un oggetto TextBox</span><span class="sxs-lookup"><span data-stu-id="63a51-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="63a51-103">Nell'esempio seguente viene illustrato come migliorare l'usabilità di un <xref:System.Windows.Controls.TextBox> visualizzando un'immagine di sfondo esplicativo all'interno del <xref:System.Windows.Controls.TextBox> fino a quando l'utente immette testo, a quel punto l'immagine viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="63a51-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="63a51-104">Inoltre, l'immagine di sfondo viene ripristinata nuovamente se l'utente rimuove l'input.</span><span class="sxs-lookup"><span data-stu-id="63a51-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="63a51-105">Vedere la figura seguente.</span><span class="sxs-lookup"><span data-stu-id="63a51-105">See illustration below.</span></span>  
  
 <span data-ttu-id="63a51-106">![Una casella di testo con un'immagine di sfondo](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="63a51-106">![A TextBox with a background image](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63a51-107">Il motivo per un'immagine di sfondo viene usata in questo esempio piuttosto che modificare semplicemente la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà di <xref:System.Windows.Controls.TextBox>, è che un'immagine di sfondo non interferisce con il data binding.</span><span class="sxs-lookup"><span data-stu-id="63a51-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63a51-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="63a51-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="63a51-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63a51-109">See also</span></span>
- [<span data-ttu-id="63a51-110">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="63a51-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="63a51-111">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="63a51-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
