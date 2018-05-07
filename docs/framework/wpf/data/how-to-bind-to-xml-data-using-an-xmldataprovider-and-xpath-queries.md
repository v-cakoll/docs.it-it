---
title: "Procedura: eseguire l'associazione a dati XML tramite un oggetto XMLDataProvider e query XPath"
ms.date: 03/30/2017
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
ms.openlocfilehash: bb8eb727fb6614440721c4d34a7d1828182d2f14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>Procedura: eseguire l'associazione a dati XML tramite un oggetto XMLDataProvider e query XPath
In questo esempio viene illustrato come associare a [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] dati utilizzando un <xref:System.Windows.Data.XmlDataProvider>.  
  
 Con un <xref:System.Windows.Data.XmlDataProvider>, i dati sottostanti a cui è possibile accedere tramite l'associazione di dati nell'applicazione può essere qualsiasi struttura ad albero di [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] nodi. In altre parole, un <xref:System.Windows.Data.XmlDataProvider> fornisce un modo pratico per utilizzare qualsiasi struttura ad albero di [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] nodi come origine di associazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, i dati sono incorporati direttamente come un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] *isola di dati* all'interno di <xref:System.Windows.FrameworkElement.Resources%2A> sezione. Un' isola di dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] deve essere racchiusa tra tag `<x:XData>` e disporre di un unico nodo radice, in questo esempio, *inventario*.  
  
> [!NOTE]
>  Il nodo radice dei dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ha un attributo **xmlns** che imposta lo spazio dei nomi [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] su una stringa vuota. Questo è di un requisito per l'applicazione di query XPath a un'isola di dati incorporata nella pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. In questo caso inline, il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], e pertanto l'isola di dati, eredita il <xref:System.Windows> dello spazio dei nomi. Per questo motivo, è necessario impostare lo spazio dei nomi vuoto per impedire che le query XPath siano qualificate per il <xref:System.Windows> spazio dei nomi che sarebbe indirizzare le query.  
  
 [!code-xaml[XMLDataSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Come illustrato in questo esempio, per creare la stessa dichiarazione di associazione nella sintassi dell'attributo è necessario usare correttamente i caratteri di escape per i caratteri speciali. Per altre informazioni, vedere [Entità carattere XML e XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md).  
  
 Il <xref:System.Windows.Controls.ListBox> visualizzerà gli elementi seguenti quando si esegue questo esempio. Questi sono gli elementi *Title* di tutti gli altri elementi in *Books* con un valore *Stock* di "*out*" o un valore *Number* di 3 o maggiore o uguale a 8. Si noti che non *CD* vengono restituiti gli elementi perché il <xref:System.Windows.Data.XmlDataProvider.XPath%2A> valore impostato sul <xref:System.Windows.Data.XmlDataProvider> indica che solo il *documentazione* gli elementi devono essere esposti (sostanzialmente impostando un filtro).  
  
 ![Esempio di XPath](../../../../docs/framework/wpf/data/media/xpathexample.PNG "XPathExample")  
  
 In questo esempio vengono visualizzati i titoli dei libri perché il <xref:System.Windows.Data.Binding.XPath%2A> del <xref:System.Windows.Controls.TextBlock> associazione il <xref:System.Windows.DataTemplate> è impostata su "*titolo*". Se si desidera visualizzare il valore di un attributo, ad esempio il *ISBN*, è necessario impostare il <xref:System.Windows.Data.Binding.XPath%2A> valore "`@ISBN`".  
  
 Le proprietà **XPath** in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono gestite dal metodo XmlNode. SelectNodes. È possibile modificare le query **XPath** per ottenere risultati diversi. Di seguito sono riportati alcuni esempi per il <xref:System.Windows.Data.Binding.XPath%2A> eseguire una query sull'oggetto associato <xref:System.Windows.Controls.ListBox> dell'esempio precedente:  
  
-   `XPath="Book[1]"` restituirà il primo elemento libro ("XML nell'azione"). Notare che gli indici di **XPath** sono basati su 1, non su 0.  
  
-   `XPath="Book[@*]"` restituirà tutti gli elementi libro con qualsiasi attributo.  
  
-   `XPath="Book[last()-1]"` restituirà dal secondo all'ultimo elemento libro ("Introduzione a Microsoft .NET").  
  
-   `XPath="*[position()>3]"` restituirà tutti gli elementi libro ad eccezione dei primi 3.  
  
 Quando si esegue un **XPath** esegue una query, viene restituito un <xref:System.Xml.XmlNode> o un elenco di XmlNode. <xref:System.Xml.XmlNode> è un [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] oggetto, che significa che è possibile usare il <xref:System.Windows.Data.Binding.Path%2A> proprietà da associare il [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] proprietà. Considerare di nuovo l'esempio precedente. Se il resto dell'esempio è uguale a e si modifica il <xref:System.Windows.Controls.TextBlock> associazione al seguente, si noterà i nomi di XmlNodes restituito nel <xref:System.Windows.Controls.ListBox>. In questo caso, il nome di tutti i nodi restituiti è "*Book*".  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 In alcune applicazioni, incorporare [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] come isola di dati all'interno dell'origine della pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] può risultare poco pratico perché il contenuto esatto dei dati deve essere noto in fase di compilazione. È anche possibile pertanto ottenere i dati da un file [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] esterno come nell'esempio seguente:  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Se il [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati risiedono in un remoto [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] file, definire l'accesso ai dati tramite l'assegnazione di un oggetto appropriato [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] per il <xref:System.Windows.Data.XmlDataProvider.Source%2A> attributo come indicato di seguito:  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Data.ObjectDataProvider>  
 [Eseguire l'associazione ai risultati di una query XDocument, XElement o LINQ for XML](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)  
 [Usare il modello Master-Details con dati XML gerarchici](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)  
 [Panoramica delle origini di associazione](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
