---
title: "Procedura: Attivare l'enumerazione TextTrimming"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimming text
- trimming text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 25fff566868e792004a915fee195485c4a1f385f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474143"
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="dbdbd-102">Procedura: Attivare l'enumerazione TextTrimming</span><span class="sxs-lookup"><span data-stu-id="dbdbd-102">How to: Enable Text Trimming</span></span>

<span data-ttu-id="dbdbd-103">Questo esempio viene illustrato l'utilizzo e gli effetti dei valori disponibili nel <xref:System.Windows.TextTrimming> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="dbdbd-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="dbdbd-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="dbdbd-104">Example</span></span>

<span data-ttu-id="dbdbd-105">L'esempio seguente definisce una <xref:System.Windows.Controls.TextBlock> elemento con la <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> set di attributi.</span><span class="sxs-lookup"><span data-stu-id="dbdbd-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

<span data-ttu-id="dbdbd-106">L'impostazione corrispondente <xref:System.Windows.TextTrimming> proprietà nel codice come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="dbdbd-106">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

<span data-ttu-id="dbdbd-107">Esistono attualmente tre opzioni per il taglio del testo: **CharacterEllipsis**, **WordEllipsis**, e **None**.</span><span class="sxs-lookup"><span data-stu-id="dbdbd-107">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>

<span data-ttu-id="dbdbd-108">Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostata su **CharacterEllipsis**, il testo viene tagliato e con i puntini di sospensione in corrispondenza del carattere più vicino al bordo del taglio.</span><span class="sxs-lookup"><span data-stu-id="dbdbd-108">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="dbdbd-109">Questa impostazione consente di tagliare il testo in modo da adattarlo meglio al limite di taglio, ma potrebbe comportare la troncatura delle parole.</span><span class="sxs-lookup"><span data-stu-id="dbdbd-109">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="dbdbd-110">La figura seguente mostra l'effetto di questa impostazione su un <xref:System.Windows.Controls.TextBlock> simile a quello definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="dbdbd-110">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="dbdbd-111">![Esempio: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="dbdbd-111">![Example: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span></span>

<span data-ttu-id="dbdbd-112">Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostata su **WordEllipsis**, il testo viene tagliato e con i puntini di sospensione alla fine della prima parola completa più vicina al bordo del taglio.</span><span class="sxs-lookup"><span data-stu-id="dbdbd-112">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="dbdbd-113">Questa impostazione non visualizzerà le parole, ma non è possibile tagliare il testo come da vicino al bordo del taglio come le **CharacterEllipsis** impostazione.</span><span class="sxs-lookup"><span data-stu-id="dbdbd-113">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="dbdbd-114">La figura seguente mostra l'effetto di questa impostazione per il <xref:System.Windows.Controls.TextBlock> definiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="dbdbd-114">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>

<span data-ttu-id="dbdbd-115">![Esempio: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="dbdbd-115">![Example: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span></span>

<span data-ttu-id="dbdbd-116">Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostata su **None**, non viene eseguita alcuna operazione di taglio del testo.</span><span class="sxs-lookup"><span data-stu-id="dbdbd-116">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="dbdbd-117">In questo caso viene eseguita una semplice operazione di ritaglio in corrispondenza del limite del contenitore di testo padre.</span><span class="sxs-lookup"><span data-stu-id="dbdbd-117">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="dbdbd-118">La figura seguente mostra l'effetto di questa impostazione su un <xref:System.Windows.Controls.TextBlock> simile a quello definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="dbdbd-118">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="dbdbd-119">![Esempio: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="dbdbd-119">![Example: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span></span>
