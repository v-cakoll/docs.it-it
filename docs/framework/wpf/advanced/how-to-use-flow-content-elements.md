---
title: 'Procedura: Usare elementi di contenuto di flusso'
ms.date: 03/30/2017
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
ms.openlocfilehash: df591304736adf1725b2b4235149bd426fe15216
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052352"
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="7a3d7-102">Procedura: Usare elementi di contenuto di flusso</span><span class="sxs-lookup"><span data-stu-id="7a3d7-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="7a3d7-103">L'esempio seguente illustra l'uso dichiarativo di vari elementi di contenuto dinamico degli attributi associati.</span><span class="sxs-lookup"><span data-stu-id="7a3d7-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="7a3d7-104">Gli elementi e gli attributi illustrati includono:</span><span class="sxs-lookup"><span data-stu-id="7a3d7-104">Elements and attributes demonstrated include:</span></span>  
  
- <span data-ttu-id="7a3d7-105">Elemento <xref:System.Windows.Documents.Bold></span><span class="sxs-lookup"><span data-stu-id="7a3d7-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
- <span data-ttu-id="7a3d7-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> Attributo</span><span class="sxs-lookup"><span data-stu-id="7a3d7-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
- <span data-ttu-id="7a3d7-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> Attributo</span><span class="sxs-lookup"><span data-stu-id="7a3d7-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
- <span data-ttu-id="7a3d7-108">Elemento <xref:System.Windows.Documents.Italic></span><span class="sxs-lookup"><span data-stu-id="7a3d7-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
- <span data-ttu-id="7a3d7-109">Elemento <xref:System.Windows.Documents.LineBreak></span><span class="sxs-lookup"><span data-stu-id="7a3d7-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
- <span data-ttu-id="7a3d7-110">Elemento <xref:System.Windows.Documents.List></span><span class="sxs-lookup"><span data-stu-id="7a3d7-110"><xref:System.Windows.Documents.List> element</span></span>  
  
- <span data-ttu-id="7a3d7-111">Elemento <xref:System.Windows.Documents.ListItem></span><span class="sxs-lookup"><span data-stu-id="7a3d7-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
- <span data-ttu-id="7a3d7-112">Elemento <xref:System.Windows.Documents.Paragraph></span><span class="sxs-lookup"><span data-stu-id="7a3d7-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
- <span data-ttu-id="7a3d7-113">Elemento <xref:System.Windows.Documents.Run></span><span class="sxs-lookup"><span data-stu-id="7a3d7-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
- <span data-ttu-id="7a3d7-114">Elemento <xref:System.Windows.Documents.Section></span><span class="sxs-lookup"><span data-stu-id="7a3d7-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
- <span data-ttu-id="7a3d7-115">Elemento <xref:System.Windows.Documents.Span></span><span class="sxs-lookup"><span data-stu-id="7a3d7-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
- <span data-ttu-id="7a3d7-116"><xref:System.Windows.Documents.Typography.Variants%2A> attributo (apice e pedice)</span><span class="sxs-lookup"><span data-stu-id="7a3d7-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
- <span data-ttu-id="7a3d7-117">Elemento <xref:System.Windows.Documents.Underline></span><span class="sxs-lookup"><span data-stu-id="7a3d7-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a3d7-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a3d7-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
