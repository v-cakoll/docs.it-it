---
title: 'Procedura: Utilizzare gli attributi di separazione delle colonne di un oggetto FlowDocument'
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 27491b21da587fa198061ba52d8daed5d3f28de3
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410901"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a>Procedura: Utilizzare gli attributi di separazione delle colonne di un oggetto FlowDocument
In questo esempio viene illustrato come utilizzare le funzionalità di separazione delle colonne di una <xref:System.Windows.Documents.FlowDocument>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente definisce una <xref:System.Windows.Documents.FlowDocument>e imposta la <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, e <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> attributi.  Il <xref:System.Windows.Documents.FlowDocument> contiene un paragrafo unico del contenuto di esempio.  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 Nella figura seguente vengono illustrati gli effetti del <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, e <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> gli attributi in un rendering <xref:System.Windows.Documents.FlowDocument>.  
  
 ![Screenshot che mostra l'attributo FlowDocument con colonne.](./media/how-to-use-flowdocument-column-separating-attributes/flowdocument-intra-column.png)
