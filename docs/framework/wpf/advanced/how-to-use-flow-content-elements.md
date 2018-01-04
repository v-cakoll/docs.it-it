---
title: 'Procedura: Usare elementi di contenuto dinamico'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e637e114187d0864afe4211a45c346c1e5a449b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="fb906-102">Procedura: Usare elementi di contenuto dinamico</span><span class="sxs-lookup"><span data-stu-id="fb906-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="fb906-103">L'esempio seguente illustra l'uso dichiarativo di vari elementi di contenuto dinamico degli attributi associati.</span><span class="sxs-lookup"><span data-stu-id="fb906-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="fb906-104">Gli elementi e gli attributi illustrati includono:</span><span class="sxs-lookup"><span data-stu-id="fb906-104">Elements and attributes demonstrated include:</span></span>  
  
-   <span data-ttu-id="fb906-105">elemento <xref:System.Windows.Documents.Bold></span><span class="sxs-lookup"><span data-stu-id="fb906-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
-   <span data-ttu-id="fb906-106">Attributo <xref:System.Windows.Documents.Block.BreakPageBefore%2A></span><span class="sxs-lookup"><span data-stu-id="fb906-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
-   <span data-ttu-id="fb906-107">Attributo <xref:System.Windows.Documents.TextElement.FontSize%2A></span><span class="sxs-lookup"><span data-stu-id="fb906-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
-   <span data-ttu-id="fb906-108">elemento <xref:System.Windows.Documents.Italic></span><span class="sxs-lookup"><span data-stu-id="fb906-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
-   <span data-ttu-id="fb906-109">elemento <xref:System.Windows.Documents.LineBreak></span><span class="sxs-lookup"><span data-stu-id="fb906-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
-   <span data-ttu-id="fb906-110">elemento <xref:System.Windows.Documents.List></span><span class="sxs-lookup"><span data-stu-id="fb906-110"><xref:System.Windows.Documents.List> element</span></span>  
  
-   <span data-ttu-id="fb906-111">elemento <xref:System.Windows.Documents.ListItem></span><span class="sxs-lookup"><span data-stu-id="fb906-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
-   <span data-ttu-id="fb906-112">elemento <xref:System.Windows.Documents.Paragraph></span><span class="sxs-lookup"><span data-stu-id="fb906-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
-   <span data-ttu-id="fb906-113">elemento <xref:System.Windows.Documents.Run></span><span class="sxs-lookup"><span data-stu-id="fb906-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
-   <span data-ttu-id="fb906-114">elemento <xref:System.Windows.Documents.Section></span><span class="sxs-lookup"><span data-stu-id="fb906-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
-   <span data-ttu-id="fb906-115">elemento <xref:System.Windows.Documents.Span></span><span class="sxs-lookup"><span data-stu-id="fb906-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
-   <span data-ttu-id="fb906-116"><xref:System.Windows.Documents.Typography.Variants%2A>attributo (apice e pedice)</span><span class="sxs-lookup"><span data-stu-id="fb906-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
-   <span data-ttu-id="fb906-117">elemento <xref:System.Windows.Documents.Underline></span><span class="sxs-lookup"><span data-stu-id="fb906-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb906-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="fb906-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
