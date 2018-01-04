---
title: 'Procedura: aggiungere una filigrana a un oggetto TextBox'
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
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92d619cb713e22d49e5c62bf7545d946b418dbda
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="d53a0-102">Procedura: aggiungere una filigrana a un oggetto TextBox</span><span class="sxs-lookup"><span data-stu-id="d53a0-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="d53a0-103">Nell'esempio seguente viene illustrato come migliorare l'usabilità di un <xref:System.Windows.Controls.TextBox> visualizzando un'immagine di sfondo esplicativo all'interno del <xref:System.Windows.Controls.TextBox> fino a quando l'utente immette testo, a quel punto l'immagine viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="d53a0-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="d53a0-104">Inoltre, l'immagine di sfondo viene ripristinata nuovamente se l'utente rimuove l'input.</span><span class="sxs-lookup"><span data-stu-id="d53a0-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="d53a0-105">Vedere la figura seguente.</span><span class="sxs-lookup"><span data-stu-id="d53a0-105">See illustration below.</span></span>  
  
 <span data-ttu-id="d53a0-106">![Una casella di testo con un'immagine di sfondo](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="d53a0-106">![A TextBox with a background image](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d53a0-107">Il motivo di un'immagine di sfondo viene utilizzata in questo esempio piuttosto che modificare semplicemente il <xref:System.Windows.Controls.TextBox.Text%2A> proprietà <xref:System.Windows.Controls.TextBox>, è che un'immagine di sfondo non interferisce con l'associazione dati.</span><span class="sxs-lookup"><span data-stu-id="d53a0-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d53a0-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="d53a0-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d53a0-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d53a0-109">See Also</span></span>  
 [<span data-ttu-id="d53a0-110">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="d53a0-110">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="d53a0-111">Cenni preliminari sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d53a0-111">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
