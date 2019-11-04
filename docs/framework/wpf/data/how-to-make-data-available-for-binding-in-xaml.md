---
title: "Procedura: rendere i dati disponibili per l'associazione in XAML"
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 2bfd9809a6ad487a7e706366dc6bce8fe951c940
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459757"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Procedura: rendere i dati disponibili per l'associazione in XAML
In questo argomento vengono illustrati i vari modi in cui è possibile rendere disponibili i dati per l'associazione in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], a seconda delle esigenze dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Se si dispone di un oggetto Common Language Runtime (CLR) a cui si desidera eseguire il binding da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], un modo per rendere disponibile l'oggetto per l'associazione consiste nel definirlo come risorsa e assegnargli un `x:Key`. Nell'esempio seguente è presente un oggetto `Person` con una proprietà stringa denominata `PersonName`. L'oggetto `Person` (nella riga visualizzata evidenziata che contiene l'elemento `<src>`) viene definito nello spazio dei nomi denominato `SDKSample`.  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 È quindi possibile associare il controllo <xref:System.Windows.Controls.TextBlock> all'oggetto in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], come illustrato nella riga evidenziata che contiene l'elemento `<TextBlock>`. 
  
 In alternativa, è possibile usare la classe <xref:System.Windows.Data.ObjectDataProvider>, come nell'esempio seguente:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 L'associazione viene definita allo stesso modo, come illustrato nella riga evidenziata che contiene l'elemento `<TextBlock>`.  
  
 In questo particolare esempio, il risultato è lo stesso: è presente una <xref:System.Windows.Controls.TextBlock> con il contenuto di testo `Joe`. Tuttavia, la classe <xref:System.Windows.Data.ObjectDataProvider> fornisce funzionalità, ad esempio la possibilità di eseguire l'associazione al risultato di un metodo. È possibile scegliere di usare la classe <xref:System.Windows.Data.ObjectDataProvider> se è necessaria la funzionalità fornita.  
  
 Tuttavia, se si esegue il binding a un oggetto che è già stato creato, è necessario impostare il `DataContext` nel codice, come nell'esempio seguente.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Per accedere ai dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] per l'associazione usando la classe <xref:System.Windows.Data.XmlDataProvider>, vedere eseguire l'associazione [a dati XML tramite un oggetto XmlDataProvider e query XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Per accedere ai dati di [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] per l'associazione usando la classe <xref:System.Windows.Data.ObjectDataProvider>, vedere [Bind to XDocument, XElement o LINQ for XML query results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Per informazioni su molti modi in cui è possibile specificare i dati a cui si sta associando, vedere [specificare l'origine del binding](how-to-specify-the-binding-source.md). Per informazioni sui tipi di dati a cui è possibile eseguire l'associazione o su come implementare oggetti di Common Language Runtime (CLR) per l'associazione, vedere [Cenni preliminari sulle origini di associazione](binding-sources-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
