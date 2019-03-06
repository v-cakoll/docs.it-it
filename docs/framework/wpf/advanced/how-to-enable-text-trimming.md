---
title: "Procedura: Attivare l'enumerazione TextTrimming"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimmng text
- trimmng text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 367e1f46524d8135d8269a2e2159dfe7c2468c45
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354466"
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="e1681-102">Procedura: Attivare l'enumerazione TextTrimming</span><span class="sxs-lookup"><span data-stu-id="e1681-102">How to: Enable Text Trimming</span></span>
<span data-ttu-id="e1681-103">Questo esempio viene illustrato l'utilizzo e gli effetti dei valori disponibili nel <xref:System.Windows.TextTrimming> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="e1681-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1681-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1681-104">Example</span></span>  
 <span data-ttu-id="e1681-105">L'esempio seguente definisce una <xref:System.Windows.Controls.TextBlock> elemento con la <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> set di attributi.</span><span class="sxs-lookup"><span data-stu-id="e1681-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>  
  
 [!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## <a name="example"></a><span data-ttu-id="e1681-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="e1681-106">Example</span></span>  
 <span data-ttu-id="e1681-107">L'impostazione corrispondente <xref:System.Windows.TextTrimming> proprietà nel codice come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e1681-107">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 <span data-ttu-id="e1681-108">Esistono attualmente tre opzioni per il taglio del testo: **CharacterEllipsis**, **WordEllipsis**, e **None**.</span><span class="sxs-lookup"><span data-stu-id="e1681-108">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>  
  
 <span data-ttu-id="e1681-109">Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostata su **CharacterEllipsis**, il testo viene tagliato e con i puntini di sospensione in corrispondenza del carattere più vicino al bordo del taglio.</span><span class="sxs-lookup"><span data-stu-id="e1681-109">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="e1681-110">Questa impostazione consente di tagliare il testo in modo da adattarlo meglio al limite di taglio, ma potrebbe comportare la troncatura delle parole.</span><span class="sxs-lookup"><span data-stu-id="e1681-110">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="e1681-111">La figura seguente mostra l'effetto di questa impostazione su un <xref:System.Windows.Controls.TextBlock> simile a quello definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e1681-111">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>  
  
 <span data-ttu-id="e1681-112">![Esempio: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="e1681-112">![Example: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span></span>  
  
 <span data-ttu-id="e1681-113">Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostata su **WordEllipsis**, il testo viene tagliato e con i puntini di sospensione alla fine della prima parola completa più vicina al bordo del taglio.</span><span class="sxs-lookup"><span data-stu-id="e1681-113">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="e1681-114">Questa impostazione non visualizzerà le parole, ma non è possibile tagliare il testo come da vicino al bordo del taglio come le **CharacterEllipsis** impostazione.</span><span class="sxs-lookup"><span data-stu-id="e1681-114">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="e1681-115">La figura seguente mostra l'effetto di questa impostazione per il <xref:System.Windows.Controls.TextBlock> definiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e1681-115">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>  
  
 <span data-ttu-id="e1681-116">![Esempio: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="e1681-116">![Example: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span></span>  
  
 <span data-ttu-id="e1681-117">Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostata su **None**, non viene eseguita alcuna operazione di taglio del testo.</span><span class="sxs-lookup"><span data-stu-id="e1681-117">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="e1681-118">In questo caso viene eseguita una semplice operazione di ritaglio in corrispondenza del limite del contenitore di testo padre.</span><span class="sxs-lookup"><span data-stu-id="e1681-118">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="e1681-119">La figura seguente mostra l'effetto di questa impostazione su un <xref:System.Windows.Controls.TextBlock> simile a quello definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e1681-119">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>  
  
 <span data-ttu-id="e1681-120">![Esempio: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="e1681-120">![Example: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span></span>
