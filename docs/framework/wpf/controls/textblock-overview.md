---
title: Cenni preliminari sul controllo TextBlock
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], TextBlock
- TextBlock control [WPF]
ms.assetid: 24720bca-341a-4b03-8a6b-7a678023b10a
ms.openlocfilehash: ce7da2b9c9c8e2a3a24d3acf18396ca447ac3f27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203470"
---
# <a name="textblock-overview"></a><span data-ttu-id="e4383-102">Cenni preliminari sul controllo TextBlock</span><span class="sxs-lookup"><span data-stu-id="e4383-102">TextBlock Overview</span></span>
<span data-ttu-id="e4383-103">Il <xref:System.Windows.Controls.TextBlock> controllo offre un supporto testuale flessibile per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e4383-103">The <xref:System.Windows.Controls.TextBlock> control provides flexible text support for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications.</span></span> <span data-ttu-id="e4383-104">L'elemento è destinato principalmente a scenari [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di base che non richiedono più di un paragrafo di testo.</span><span class="sxs-lookup"><span data-stu-id="e4383-104">The element is targeted primarily toward basic [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] scenarios that do not require more than one paragraph of text.</span></span> <span data-ttu-id="e4383-105">Supporta un numero di proprietà che consentono un controllo preciso della presentazione, ad esempio <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, e <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4383-105">It supports a number of properties that enable precise control of presentation, such as <xref:System.Windows.Controls.TextBlock.FontFamily%2A>, <xref:System.Windows.Controls.TextBlock.FontSize%2A>, <xref:System.Windows.Controls.TextBlock.FontWeight%2A>, <xref:System.Windows.Controls.TextBlock.TextEffects%2A>, and <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>.</span></span> <span data-ttu-id="e4383-106">Contenuto di testo può essere aggiunto usando il <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="e4383-106">Text content can be added using the <xref:System.Windows.Controls.TextBlock.Text%2A> property.</span></span> <span data-ttu-id="e4383-107">Se usato in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], il contenuto tra tag di apertura e di chiusura viene aggiunto in modo implicito come testo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="e4383-107">When used in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], content between the open and closing tag is implicitly added as the text of the element.</span></span>  
  
 <span data-ttu-id="e4383-108">Oggetto <xref:System.Windows.Controls.TextBlock> elemento può essere implementato con molto semplicemente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4383-108">A <xref:System.Windows.Controls.TextBlock> element can be instantiated very simply using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[TextBlockSnip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip_XAML/CS/default.xaml#2)]  
  
 <span data-ttu-id="e4383-109">Analogamente, l'utilizzo del <xref:System.Windows.Controls.TextBlock> elemento nel codice è relativamente semplice.</span><span class="sxs-lookup"><span data-stu-id="e4383-109">Similarly, usage of the <xref:System.Windows.Controls.TextBlock> element in code is relatively simple.</span></span>  
  
 [!code-csharp[TextBlockSnip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBlockSnip/CSharp/TextBlockSnips.cs#1)]
 [!code-vb[TextBlockSnip#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBlockSnip/VisualBasic/TextBlockSnips.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e4383-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4383-110">See also</span></span>

- <xref:System.Windows.Controls.Label>
