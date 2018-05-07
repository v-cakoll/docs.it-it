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
ms.openlocfilehash: dd66fb2f96f8c42fea36afaeda0aaf35a2adbace
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Procedura: rendere i dati disponibili per l'associazione in XAML
In questo argomento vengono illustrati i diversi modi, è possibile rendere disponibili dati per l'associazione in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], a seconda delle esigenze dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Se dispone di un [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] oggetto che si desidera eseguire l'associazione da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], un modo è possibile renderlo disponibile per l'associazione per definirlo come una risorsa e assegnargli un `x:Key`. In questo esempio, è necessario un `Person` oggetto con una proprietà stringa denominata `PersonName`. Il `Person` oggetto, che viene visualizzato per la riga evidenziata che contiene il `<src>` è definito l'elemento, lo spazio dei nomi denominato `SDKSample`.  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 È quindi possibile associare il <xref:System.Windows.Controls.TextBlock> controllo all'oggetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], come riga evidenziata che contiene il `<TextBlock>` Mostra elemento. 
  
 In alternativa, è possibile utilizzare il <xref:System.Windows.Data.ObjectDataProvider> (classe), come nell'esempio seguente:  
  
 [!code-xaml[ObjectDataProvider}](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Definire l'associazione nello stesso modo, la riga evidenziata che contiene il `<TextBlock>` Mostra elemento.  
  
 In questo particolare esempio, il risultato è lo stesso: è un <xref:System.Windows.Controls.TextBlock> con il contenuto di testo `Joe`. Tuttavia, la <xref:System.Windows.Data.ObjectDataProvider> classe fornisce funzionalità quali la possibilità di associare al risultato di un metodo. È possibile scegliere di utilizzare la <xref:System.Windows.Data.ObjectDataProvider> classe se necessaria la funzionalità fornita.  
  
 Tuttavia, se si associa a un oggetto che è già stato creato, è necessario impostare il `DataContext` nel codice, come nell'esempio seguente.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Per accedere a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati per l'associazione mediante i <xref:System.Windows.Data.XmlDataProvider> classe, vedere [associazione a dati XML tramite un XMLDataProvider e query XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Per accedere a [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati per l'associazione mediante i <xref:System.Windows.Data.ObjectDataProvider> classe, vedere [associare XDocument, XElement o LINQ dei risultati della Query XML](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Per informazioni sulle diverse modalità con cui è possibile specificare i dati che si desidera associare a, vedere [specificare l'origine di associazione](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md). Per informazioni sui tipi di dati è possibile associare o come implementare la propria [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] degli oggetti per l'associazione, vedere [Cenni preliminari sulle origini di associazione](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
