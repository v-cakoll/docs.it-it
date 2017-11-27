---
title: 'Procedura: attivare l''enumerazione TextTrimming'
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
- text [WPF], trimming
- documents [WPF], trimmng text
- trimmng text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8f0f24bb6271e63dc50bd063aedfd8185711e7a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="fc635-102">Procedura: attivare l'enumerazione TextTrimming</span><span class="sxs-lookup"><span data-stu-id="fc635-102">How to: Enable Text Trimming</span></span>
<span data-ttu-id="fc635-103">Questo esempio viene illustrato l'utilizzo e gli effetti dei valori disponibili nel <xref:System.Windows.TextTrimming> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="fc635-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc635-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc635-104">Example</span></span>  
 <span data-ttu-id="fc635-105">L'esempio seguente definisce un <xref:System.Windows.Controls.TextBlock> elemento con la <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> set di attributi.</span><span class="sxs-lookup"><span data-stu-id="fc635-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>  
  
 [!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## <a name="example"></a><span data-ttu-id="fc635-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="fc635-106">Example</span></span>  
 <span data-ttu-id="fc635-107">L'impostazione corrispondente <xref:System.Windows.TextTrimming> proprietà nel codice è illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="fc635-107">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 <span data-ttu-id="fc635-108">Esistono attualmente tre opzioni per il taglio del testo: **CharacterEllipsis**, **WordEllipsis**, e **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="fc635-108">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>  
  
 <span data-ttu-id="fc635-109">Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostato su **CharacterEllipsis**, il testo viene tagliato e con i puntini di sospensione in corrispondenza del carattere più vicino al bordo di taglio.</span><span class="sxs-lookup"><span data-stu-id="fc635-109">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="fc635-110">Questa impostazione consente di tagliare il testo in modo da adattarlo meglio al limite di taglio, ma potrebbe comportare la troncatura delle parole.</span><span class="sxs-lookup"><span data-stu-id="fc635-110">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="fc635-111">Nella figura seguente mostra l'effetto di questa impostazione in un <xref:System.Windows.Controls.TextBlock> simile a quello definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="fc635-111">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>  
  
 <span data-ttu-id="fc635-112">![Esempio: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="fc635-112">![Example: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")</span></span>  
  
 <span data-ttu-id="fc635-113">Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostato su **WordEllipsis**, il testo viene tagliato e con i puntini di sospensione alla fine della prima parola completa più vicina del bordo di taglio.</span><span class="sxs-lookup"><span data-stu-id="fc635-113">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="fc635-114">Questa impostazione non visualizzerà le parole, ma non è possibile tagliare testo quanto più accuratamente il bordo di taglio come il **CharacterEllipsis** impostazione.</span><span class="sxs-lookup"><span data-stu-id="fc635-114">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="fc635-115">Nella figura seguente mostra l'effetto di questa impostazione per il <xref:System.Windows.Controls.TextBlock> definiti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="fc635-115">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>  
  
 <span data-ttu-id="fc635-116">![Esempio: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="fc635-116">![Example: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")</span></span>  
  
 <span data-ttu-id="fc635-117">Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostato su **Nessuno**, non viene eseguita alcuna operazione di taglio del testo.</span><span class="sxs-lookup"><span data-stu-id="fc635-117">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="fc635-118">In questo caso viene eseguita una semplice operazione di ritaglio in corrispondenza del limite del contenitore di testo padre.</span><span class="sxs-lookup"><span data-stu-id="fc635-118">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="fc635-119">Nella figura seguente mostra l'effetto di questa impostazione in un <xref:System.Windows.Controls.TextBlock> simile a quello definito in precedenza.</span><span class="sxs-lookup"><span data-stu-id="fc635-119">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>  
  
 <span data-ttu-id="fc635-120">![Esempio: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="fc635-120">![Example: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")</span></span>
