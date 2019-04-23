---
title: 'Procedura: Eseguire il binding ai dati XML usando un oggetto XMLDataProvider e le query XPath'
ms.date: 03/30/2017
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
ms.openlocfilehash: f6cd09279cf23d3273e7a4083950a5f42714c8bf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097226"
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>Procedura: Eseguire il binding ai dati XML usando un oggetto XMLDataProvider e le query XPath
Questo esempio viene illustrato come associare [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] dati usando un <xref:System.Windows.Data.XmlDataProvider>.  
  
 Con un <xref:System.Windows.Data.XmlDataProvider>, i dati sottostanti a cui è possibile accedere tramite associazione dati nell'applicazione può essere qualsiasi struttura ad albero di [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] nodi. In altre parole, un' <xref:System.Windows.Data.XmlDataProvider> fornisce un modo pratico per usare qualsiasi struttura ad albero di [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] nodi come origine del binding.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, i dati sono incorporati direttamente come un [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] *isola di dati* all'interno di <xref:System.Windows.FrameworkElement.Resources%2A> sezione. Un' isola di dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] deve essere racchiusa tra tag `<x:XData>` e disporre di un unico nodo radice, in questo esempio, *inventario*.  
  
> [!NOTE]
>  Il nodo radice dei dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ha un attributo **xmlns** che imposta lo spazio dei nomi [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] su una stringa vuota. Questo è di un requisito per l'applicazione di query XPath a un'isola di dati incorporata nella pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. In questo caso, il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], e pertanto ne eredita l'isola di dati, il <xref:System.Windows> dello spazio dei nomi. Per questo motivo, è necessario impostare vuoto per impedire che le query XPath siano qualificate dallo spazio dei nomi di <xref:System.Windows> dello spazio dei nomi, che le indirizzerebbe.  
  
 [!code-xaml[XMLDataSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Come illustrato in questo esempio, per creare la stessa dichiarazione di associazione nella sintassi dell'attributo è necessario usare correttamente i caratteri di escape per i caratteri speciali. Per altre informazioni, vedere [Entità carattere XML e XAML](../../xaml-services/xml-character-entities-and-xaml.md).  
  
 Il <xref:System.Windows.Controls.ListBox> mostrerà gli elementi seguenti durante l'esecuzione in questo esempio. Questi sono gli elementi *Title* di tutti gli altri elementi in *Books* con un valore *Stock* di "*out*" o un valore *Number* di 3 o maggiore o uguale a 8. Si noti che nessuna *CD* vengono restituiti gli elementi perché il <xref:System.Windows.Data.XmlDataProvider.XPath%2A> valore impostato sul <xref:System.Windows.Data.XmlDataProvider> indica che solo il *documentazione* devono esporre gli elementi (essenzialmente impostando un filtro).  
  
 ![Esempio di XPath](./media/xpathexample.PNG "XPathExample")  
  
 In questo esempio vengono visualizzati i titoli dei libri perché il <xref:System.Windows.Data.Binding.XPath%2A> del <xref:System.Windows.Controls.TextBlock> binding nel <xref:System.Windows.DataTemplate> è impostata su "*titolo*". Se si desidera visualizzare il valore di un attributo, ad esempio la *ISBN*, è necessario impostare il <xref:System.Windows.Data.Binding.XPath%2A> valore "`@ISBN`".  
  
 Le proprietà **XPath** in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono gestite dal metodo XmlNode. SelectNodes. È possibile modificare le query **XPath** per ottenere risultati diversi. Di seguito sono riportati alcuni esempi per la <xref:System.Windows.Data.Binding.XPath%2A> eseguire una query sull'oggetto associato <xref:System.Windows.Controls.ListBox> dall'esempio precedente:  
  
-   `XPath="Book[1]"` restituirà il primo elemento libro ("XML nell'azione"). Notare che gli indici di **XPath** sono basati su 1, non su 0.  
  
-   `XPath="Book[@*]"` restituirà tutti gli elementi libro con qualsiasi attributo.  
  
-   `XPath="Book[last()-1]"` restituirà dal secondo all'ultimo elemento libro ("Introduzione a Microsoft .NET").  
  
-   `XPath="*[position()>3]"` restituirà tutti gli elementi libro ad eccezione dei primi 3.  
  
 Quando si esegue un' **XPath** esegue una query, viene restituito un <xref:System.Xml.XmlNode> o un elenco di XmlNodes. <xref:System.Xml.XmlNode> è un [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] oggetto, ovvero è possibile usare il <xref:System.Windows.Data.Binding.Path%2A> proprietà da associare il [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] proprietà. Considerare di nuovo l'esempio precedente. Se il resto dell'esempio rimane invariata e si modifica il <xref:System.Windows.Controls.TextBlock> associazione al seguente, si noterà i nomi di XmlNodes restituiti nel <xref:System.Windows.Controls.ListBox>. In questo caso, il nome di tutti i nodi restituiti è "*Book*".  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 In alcune applicazioni, incorporare [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] come isola di dati all'interno dell'origine della pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] può risultare poco pratico perché il contenuto esatto dei dati deve essere noto in fase di compilazione. È anche possibile pertanto ottenere i dati da un file [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] esterno come nell'esempio seguente:  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Se il [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati si trovano in un server remoto [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] file, è definire l'accesso ai dati tramite l'assegnazione di un oggetto appropriato [!INCLUDE[TLA2#tla_url](../../../../includes/tla2sharptla-url-md.md)] per il <xref:System.Windows.Data.XmlDataProvider.Source%2A> attributo come indicato di seguito:  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.ObjectDataProvider>
- [Eseguire l'associazione ai risultati di una query XDocument, XElement o LINQ for XML](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)
- [Usare il modello Master-Details con dati XML gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Panoramica delle origini di associazione](binding-sources-overview.md)
- [Panoramica sul data binding](data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
