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
ms.openlocfilehash: abe276c686d394ded13ec03f08deae65e4098d03
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923569"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="561c0-102">Procedura: Aggiungere una filigrana a un oggetto TextBox</span><span class="sxs-lookup"><span data-stu-id="561c0-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="561c0-103">Nell'esempio seguente viene illustrato come facilitare l'usabilità di <xref:System.Windows.Controls.TextBox> un oggetto visualizzando un'immagine di sfondo esplicativa <xref:System.Windows.Controls.TextBox> all'interno di fino a quando l'utente non immette testo, a quel punto l'immagine viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="561c0-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="561c0-104">Inoltre, l'immagine di sfondo viene ripristinata di nuovo se l'utente rimuove il proprio input.</span><span class="sxs-lookup"><span data-stu-id="561c0-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="561c0-105">Vedere la figura seguente.</span><span class="sxs-lookup"><span data-stu-id="561c0-105">See illustration below.</span></span>  
  
 <span data-ttu-id="561c0-106">![Casella di testo con un'immagine di sfondo](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="561c0-106">![A TextBox with a background image](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="561c0-107">Il motivo per cui un'immagine di sfondo viene utilizzata in questo esempio invece di modificare <xref:System.Windows.Controls.TextBox.Text%2A> semplicemente la <xref:System.Windows.Controls.TextBox>proprietà di, è che un'immagine di sfondo non interferisce con data binding.</span><span class="sxs-lookup"><span data-stu-id="561c0-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="561c0-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="561c0-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="561c0-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="561c0-109">See also</span></span>

- [<span data-ttu-id="561c0-110">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="561c0-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="561c0-111">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="561c0-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
