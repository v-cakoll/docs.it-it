---
title: 'Procedura: Rendere i dati disponibili per il binding in XAML'
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 3487a160cc49ab6b779a20157668915c2da33900
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401500"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Procedura: Rendere i dati disponibili per il binding in XAML
In questo argomento vengono illustrati i vari modi in cui è possibile [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]rendere disponibili i dati per l'associazione in, a seconda delle esigenze dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Se si dispone di un oggetto Common Language Runtime (CLR) a cui si [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]desidera eseguire il binding, è possibile rendere disponibile l'oggetto per l'associazione in modo da definirlo come risorsa e assegnargli un. `x:Key` Nell'esempio seguente è presente un `Person` oggetto con una proprietà stringa denominata. `PersonName` L' `Person` oggetto (nella riga visualizzata evidenziata che contiene l' `<src>` elemento) viene definito nello spazio dei nomi `SDKSample`denominato.  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 È quindi possibile associare il <xref:System.Windows.Controls.TextBlock> controllo all'oggetto in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], come illustrato nella riga evidenziata che contiene `<TextBlock>` l'elemento. 
  
 In alternativa, è possibile usare la <xref:System.Windows.Data.ObjectDataProvider> classe, come nell'esempio seguente:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 L'associazione viene definita allo stesso modo, come illustrato nella riga evidenziata che `<TextBlock>` contiene l'elemento.  
  
 In questo particolare esempio, il risultato è lo stesso: è presente un <xref:System.Windows.Controls.TextBlock> oggetto con il contenuto `Joe`di testo. Tuttavia, la <xref:System.Windows.Data.ObjectDataProvider> classe fornisce funzionalità come la possibilità di eseguire l'associazione al risultato di un metodo. Se è necessaria la funzionalità fornita <xref:System.Windows.Data.ObjectDataProvider> , è possibile scegliere di utilizzare la classe.  
  
 Tuttavia, se si esegue il `DataContext` binding a un oggetto che è già stato creato, è necessario impostare nel codice, come nell'esempio seguente.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Per accedere [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ai dati per l'associazione <xref:System.Windows.Data.XmlDataProvider> usando la classe, vedere eseguire l'associazione [a dati XML tramite un oggetto XmlDataProvider e query XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Per accedere [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ai dati per l'associazione <xref:System.Windows.Data.ObjectDataProvider> usando la classe, vedere [Bind to XDocument, XElement o LINQ for XML query results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Per informazioni su molti modi in cui è possibile specificare i dati a cui si sta associando, vedere [specificare l'origine del binding](how-to-specify-the-binding-source.md). Per informazioni sui tipi di dati a cui è possibile eseguire l'associazione o su come implementare oggetti di Common Language Runtime (CLR) per l'associazione, vedere [Cenni preliminari sulle origini di associazione](binding-sources-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
