---
title: 'Procedura: Usare elementi di contenuto dinamico'
ms.date: 03/30/2017
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
ms.openlocfilehash: 146a785ef4f6da650144ed6fc47633670304bde6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544131"
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="f7884-102">Procedura: Usare elementi di contenuto dinamico</span><span class="sxs-lookup"><span data-stu-id="f7884-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="f7884-103">L'esempio seguente illustra l'uso dichiarativo di vari elementi di contenuto dinamico degli attributi associati.</span><span class="sxs-lookup"><span data-stu-id="f7884-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="f7884-104">Gli elementi e gli attributi illustrati includono:</span><span class="sxs-lookup"><span data-stu-id="f7884-104">Elements and attributes demonstrated include:</span></span>  
  
-   <span data-ttu-id="f7884-105">elemento <xref:System.Windows.Documents.Bold></span><span class="sxs-lookup"><span data-stu-id="f7884-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
-   <span data-ttu-id="f7884-106">Attributo <xref:System.Windows.Documents.Block.BreakPageBefore%2A></span><span class="sxs-lookup"><span data-stu-id="f7884-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
-   <span data-ttu-id="f7884-107">Attributo <xref:System.Windows.Documents.TextElement.FontSize%2A></span><span class="sxs-lookup"><span data-stu-id="f7884-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
-   <span data-ttu-id="f7884-108">elemento <xref:System.Windows.Documents.Italic></span><span class="sxs-lookup"><span data-stu-id="f7884-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
-   <span data-ttu-id="f7884-109">elemento <xref:System.Windows.Documents.LineBreak></span><span class="sxs-lookup"><span data-stu-id="f7884-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
-   <span data-ttu-id="f7884-110">elemento <xref:System.Windows.Documents.List></span><span class="sxs-lookup"><span data-stu-id="f7884-110"><xref:System.Windows.Documents.List> element</span></span>  
  
-   <span data-ttu-id="f7884-111">elemento <xref:System.Windows.Documents.ListItem></span><span class="sxs-lookup"><span data-stu-id="f7884-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
-   <span data-ttu-id="f7884-112">elemento <xref:System.Windows.Documents.Paragraph></span><span class="sxs-lookup"><span data-stu-id="f7884-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
-   <span data-ttu-id="f7884-113">elemento <xref:System.Windows.Documents.Run></span><span class="sxs-lookup"><span data-stu-id="f7884-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
-   <span data-ttu-id="f7884-114">elemento <xref:System.Windows.Documents.Section></span><span class="sxs-lookup"><span data-stu-id="f7884-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
-   <span data-ttu-id="f7884-115">elemento <xref:System.Windows.Documents.Span></span><span class="sxs-lookup"><span data-stu-id="f7884-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
-   <span data-ttu-id="f7884-116"><xref:System.Windows.Documents.Typography.Variants%2A> attributo (apice e pedice)</span><span class="sxs-lookup"><span data-stu-id="f7884-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
-   <span data-ttu-id="f7884-117">elemento <xref:System.Windows.Documents.Underline></span><span class="sxs-lookup"><span data-stu-id="f7884-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7884-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="f7884-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
