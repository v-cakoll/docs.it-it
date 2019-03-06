---
title: 'Procedura: Modificare la tipografia del testo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting Typography attributes [WPF]
- Typography attribute [WPF], setting
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
ms.openlocfilehash: eeed93f62802a942915511db060c0e6c029579e0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365782"
---
# <a name="how-to-alter-the-typography-of-text"></a><span data-ttu-id="1e7c5-102">Procedura: Modificare la tipografia del testo</span><span class="sxs-lookup"><span data-stu-id="1e7c5-102">How-to: Alter the Typography of Text</span></span>
<span data-ttu-id="1e7c5-103">Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Documents.TextElement.Typography%2A> dell'attributo, usando <xref:System.Windows.Documents.Paragraph> come elemento di esempio.</span><span class="sxs-lookup"><span data-stu-id="1e7c5-103">The following example shows how to set the <xref:System.Windows.Documents.TextElement.Typography%2A> attribute, using <xref:System.Windows.Documents.Paragraph> as the example element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e7c5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="1e7c5-104">Example</span></span>  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 <span data-ttu-id="1e7c5-105">La figura seguente illustra il rendering di questo esempio.</span><span class="sxs-lookup"><span data-stu-id="1e7c5-105">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="1e7c5-106">![Schermata: Testo con tipografia modificata](./media/textelement-typog.png "TextElement_Typog")</span><span class="sxs-lookup"><span data-stu-id="1e7c5-106">![Screenshot: Text with altered typography](./media/textelement-typog.png "TextElement_Typog")</span></span>  
  
 <span data-ttu-id="1e7c5-107">La figura seguente mostra invece il rendering dello stesso esempio con le proprietà tipografiche predefinite.</span><span class="sxs-lookup"><span data-stu-id="1e7c5-107">In contrast, the following figure shows how a similar example with default typographic properties renders.</span></span>  
  
 <span data-ttu-id="1e7c5-108">![Schermata: Testo con tipografia modificata](./media/textelement-typog-default.png "TextElement_Typog_Default")</span><span class="sxs-lookup"><span data-stu-id="1e7c5-108">![Screenshot: Text with altered typography](./media/textelement-typog-default.png "TextElement_Typog_Default")</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e7c5-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="1e7c5-109">Example</span></span>  
 <span data-ttu-id="1e7c5-110">Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Controls.TextBox.Typography%2A> proprietà a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="1e7c5-110">The following example shows how to set the <xref:System.Windows.Controls.TextBox.Typography%2A> property programmatically.</span></span>  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a><span data-ttu-id="1e7c5-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e7c5-111">See also</span></span>
- [<span data-ttu-id="1e7c5-112">Cenni preliminari sui documenti dinamici</span><span class="sxs-lookup"><span data-stu-id="1e7c5-112">Flow Document Overview</span></span>](flow-document-overview.md)
