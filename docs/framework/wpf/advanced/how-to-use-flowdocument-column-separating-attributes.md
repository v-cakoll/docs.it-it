---
title: 'Procedura: utilizzare gli attributi di separazione delle colonne di un oggetto FlowDocument'
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 678e01a35c286ea03f0385291d64f2f900f068c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543771"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a><span data-ttu-id="c9b6d-102">Procedura: utilizzare gli attributi di separazione delle colonne di un oggetto FlowDocument</span><span class="sxs-lookup"><span data-stu-id="c9b6d-102">How to: Use FlowDocument Column-Separating Attributes</span></span>
<span data-ttu-id="c9b6d-103">In questo esempio viene illustrato come utilizzare le funzionalità di separazione delle colonne di una <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="c9b6d-103">This example shows how to use the column-separating features of a <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9b6d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c9b6d-104">Example</span></span>  
 <span data-ttu-id="c9b6d-105">L'esempio seguente definisce un <xref:System.Windows.Documents.FlowDocument>e imposta il <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, e <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> gli attributi.</span><span class="sxs-lookup"><span data-stu-id="c9b6d-105">The following example defines a <xref:System.Windows.Documents.FlowDocument>, and sets the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes.</span></span>  <span data-ttu-id="c9b6d-106">Il <xref:System.Windows.Documents.FlowDocument> contiene un singolo paragrafo del contenuto di esempio.</span><span class="sxs-lookup"><span data-stu-id="c9b6d-106">The <xref:System.Windows.Documents.FlowDocument> contains a single paragraph of sample content.</span></span>  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 <span data-ttu-id="c9b6d-107">Nella figura seguente vengono illustrati gli effetti del <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, e <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributi in un rendering <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="c9b6d-107">The following figure shows the effects of the <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, and <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributes in a rendered <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="c9b6d-108">![Schermata: FlowDocument con colonne](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span><span class="sxs-lookup"><span data-stu-id="c9b6d-108">![Screenshot: FlowDocument Intra Column](../../../../docs/framework/wpf/advanced/media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")</span></span>
