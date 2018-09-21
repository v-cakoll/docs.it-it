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
ms.openlocfilehash: 09a6fca48c06efca6f06b9e0617de9095197bd17
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46525032"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Procedura: rendere i dati disponibili per l'associazione in XAML
In questo argomento illustra vari modi in cui è possibile rendere disponibili dati per l'associazione in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], a seconda delle esigenze dell'applicazione.  
  
## <a name="example"></a>Esempio  
 Se si dispone di un [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] si vuole eseguire l'associazione da dell'oggetto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], un modo è possibile rendere disponibile l'oggetto per l'associazione per definirlo come una risorsa e assegnargli un `x:Key`. Nell'esempio seguente, è necessario un `Person` oggetto con una proprietà stringa denominata `PersonName`. Il `Person` oggetti (nella riga evidenziata che contiene il `<src>` elemento) viene definito nello spazio dei nomi denominato `SDKSample`.  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 È quindi possibile associare il <xref:System.Windows.Controls.TextBlock> controllo all'oggetto nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], come evidenziato la riga che contiene il `<TextBlock>` Mostra elemento. 
  
 In alternativa, è possibile usare il <xref:System.Windows.Data.ObjectDataProvider> (classe), come nell'esempio seguente:  
  
 [!code-xaml[ObjectDataProvider}](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Definire l'associazione nello stesso modo, la riga evidenziata che contiene il `<TextBlock>` Mostra elemento.  
  
 In questo particolare esempio, il risultato è lo stesso: è necessario un <xref:System.Windows.Controls.TextBlock> con il contenuto di testo `Joe`. Tuttavia, il <xref:System.Windows.Data.ObjectDataProvider> classe offre funzionalità quali la possibilità di associare al risultato di un metodo. È possibile scegliere di usare il <xref:System.Windows.Data.ObjectDataProvider> classe se necessaria la funzionalità fornita.  
  
 Tuttavia, se esegue il binding a un oggetto che è già stato creato, è necessario impostare il `DataContext` nel codice, come nell'esempio seguente.  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Per accedere [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dei dati per l'associazione mediante il <xref:System.Windows.Data.XmlDataProvider> classe, vedere [eseguire l'associazione a dati XML tramite un oggetto XMLDataProvider e query XPath](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Per accedere [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dei dati per l'associazione mediante il <xref:System.Windows.Data.ObjectDataProvider> classe, vedere [eseguire l'associazione a XDocument, XElement o LINQ for dei risultati di Query XML](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Per informazioni su molti aspetti è possibile specificare i dati a cui si esegue l'associazione, vedere [specificare l'origine del Binding](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md). Per informazioni su quali tipi di dati è possibile associare a o come implementare il proprio [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] degli oggetti per l'associazione, vedere [Cenni preliminari sulle origini di associazione](../../../../docs/framework/wpf/data/binding-sources-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
