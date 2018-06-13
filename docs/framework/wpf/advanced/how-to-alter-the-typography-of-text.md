---
title: 'Procedura: modificare le opzioni tipografiche del testo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting Typography attributes [WPF]
- Typography attribute [WPF], setting
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
ms.openlocfilehash: fcc9c894970934bb5a69debef2f4e38297f82198
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542929"
---
# <a name="how-to-alter-the-typography-of-text"></a><span data-ttu-id="ddd6f-102">Procedura: modificare le opzioni tipografiche del testo</span><span class="sxs-lookup"><span data-stu-id="ddd6f-102">How-to: Alter the Typography of Text</span></span>
<span data-ttu-id="ddd6f-103">Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Documents.TextElement.Typography%2A> attributo, mediante <xref:System.Windows.Documents.Paragraph> come elemento di esempio.</span><span class="sxs-lookup"><span data-stu-id="ddd6f-103">The following example shows how to set the <xref:System.Windows.Documents.TextElement.Typography%2A> attribute, using <xref:System.Windows.Documents.Paragraph> as the example element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddd6f-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="ddd6f-104">Example</span></span>  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 <span data-ttu-id="ddd6f-105">La figura seguente illustra il rendering di questo esempio.</span><span class="sxs-lookup"><span data-stu-id="ddd6f-105">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="ddd6f-106">![Screenshot: testo con proprietà tipografiche modificate](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")</span><span class="sxs-lookup"><span data-stu-id="ddd6f-106">![Screenshot: Text with altered typography](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")</span></span>  
  
 <span data-ttu-id="ddd6f-107">La figura seguente mostra invece il rendering dello stesso esempio con le proprietà tipografiche predefinite.</span><span class="sxs-lookup"><span data-stu-id="ddd6f-107">In contrast, the following figure shows how a similar example with default typographic properties renders.</span></span>  
  
 <span data-ttu-id="ddd6f-108">![Screenshot: testo con le opzioni tipografiche predefinite](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")</span><span class="sxs-lookup"><span data-stu-id="ddd6f-108">![Screenshot: Text with altered typography](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")</span></span>  
  
## <a name="example"></a><span data-ttu-id="ddd6f-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="ddd6f-109">Example</span></span>  
 <span data-ttu-id="ddd6f-110">Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Controls.TextBox.Typography%2A> proprietà a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="ddd6f-110">The following example shows how to set the <xref:System.Windows.Controls.TextBox.Typography%2A> property programmatically.</span></span>  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a><span data-ttu-id="ddd6f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddd6f-111">See Also</span></span>  
 [<span data-ttu-id="ddd6f-112">Cenni preliminari sui documenti dinamici</span><span class="sxs-lookup"><span data-stu-id="ddd6f-112">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)
