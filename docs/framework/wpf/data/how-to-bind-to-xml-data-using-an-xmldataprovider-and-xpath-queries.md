---
title: "Procedura: eseguire l'associazione a dati XML tramite un oggetto XMLDataProvider e query XPath"
ms.date: 03/30/2017
helpviewer_keywords:
- XmlDataProvider [WPF], binding to XML data
- data binding [WPF], binding to XML data using XmlDataProvider queries
- binding [WPF], to XML data using XmlDataProvider queries
ms.assetid: 7dcd018f-16aa-4870-8e47-c1b4ea31e574
ms.openlocfilehash: a5ad7d8bce9bc0a760868e483278d1836f9472af
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559703"
---
# <a name="how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries"></a>Procedura: eseguire l'associazione a dati XML tramite un oggetto XMLDataProvider e query XPath
In questo esempio viene illustrato come eseguire l'associazione a dati XML utilizzando un <xref:System.Windows.Data.XmlDataProvider>.  
  
 Con una <xref:System.Windows.Data.XmlDataProvider>, i dati sottostanti a cui è possibile accedere tramite data binding nell'applicazione possono essere qualsiasi albero di nodi XML. In altre parole, un <xref:System.Windows.Data.XmlDataProvider> rappresenta un metodo pratico per utilizzare qualsiasi albero di nodi XML come origine di associazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente i dati vengono incorporati direttamente come un'isola di *dati* XML all'interno della sezione <xref:System.Windows.FrameworkElement.Resources%2A>. Un'isola di dati XML deve essere racchiusa tra `<x:XData>` tag e avere sempre un singolo nodo radice, ovvero l' *inventario* in questo esempio.  
  
> [!NOTE]
> Il nodo radice dei dati XML ha un attributo **xmlns** che imposta lo spazio dei nomi XML su una stringa vuota. Questo è di un requisito per l'applicazione di query XPath a un'isola di dati incorporata nella pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. In questo caso inline, il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]e quindi l'isola di dati eredita lo spazio dei nomi <xref:System.Windows>. Per questo motivo, è necessario impostare lo spazio dei nomi vuoto per evitare che le query XPath siano qualificate dallo spazio dei nomi <xref:System.Windows>, che potrebbe indirizzare le query in modo non valido.  
  
 [!code-xaml[XMLDataSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource/CS/Window1.xaml#1)]  
  
 Come illustrato in questo esempio, per creare la stessa dichiarazione di associazione nella sintassi dell'attributo è necessario usare correttamente i caratteri di escape per i caratteri speciali. Per altre informazioni, vedere [Entità carattere XML e XAML](../../../desktop-wpf/xaml-services/xml-character-entities.md).  
  
 Quando viene eseguito questo esempio, nel <xref:System.Windows.Controls.ListBox> vengono visualizzati gli elementi seguenti. Questi sono gli elementi *Title* di tutti gli altri elementi in *Books* con un valore *Stock* di "*out*" o un valore *Number* di 3 o maggiore o uguale a 8. Si noti che non viene restituito alcun elemento *CD* perché il valore <xref:System.Windows.Data.XmlDataProvider.XPath%2A> impostato sul <xref:System.Windows.Data.XmlDataProvider> indica che devono essere esposti solo gli elementi *books* (essenzialmente impostando un filtro).  
  
 ![Screenshot dell'esempio XPath che mostra il titolo di quattro libri.](./media/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries/xpath-example-listbox-details.png)  
  
 In questo esempio vengono visualizzati i titoli dei libri perché il <xref:System.Windows.Data.Binding.XPath%2A> dell'associazione <xref:System.Windows.Controls.TextBlock> nel <xref:System.Windows.DataTemplate> è impostato su "*title*". Se si desidera visualizzare il valore di un attributo, ad esempio il *codice ISBN*, impostare il valore <xref:System.Windows.Data.Binding.XPath%2A> su "`@ISBN`".  
  
 Le proprietà **XPath** in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono gestite dal metodo XmlNode. SelectNodes. È possibile modificare le query **XPath** per ottenere risultati diversi. Di seguito sono riportati alcuni esempi per la query <xref:System.Windows.Data.Binding.XPath%2A> sul <xref:System.Windows.Controls.ListBox> associato dell'esempio precedente:  
  
- `XPath="Book[1]"` restituirà il primo elemento libro ("XML nell'azione"). Notare che gli indici di **XPath** sono basati su 1, non su 0.  
  
- `XPath="Book[@*]"` restituirà tutti gli elementi libro con qualsiasi attributo.  
  
- `XPath="Book[last()-1]"` restituirà dal secondo all'ultimo elemento libro ("Introduzione a Microsoft .NET").  
  
- `XPath="*[position()>3]"` restituirà tutti gli elementi libro ad eccezione dei primi 3.  
  
 Quando si esegue una query **XPath** , viene restituito un <xref:System.Xml.XmlNode> o un elenco di XMLNodes. <xref:System.Xml.XmlNode> è un oggetto Common Language Runtime (CLR), ovvero è possibile utilizzare la proprietà <xref:System.Windows.Data.Binding.Path%2A> per eseguire l'associazione alle proprietà Common Language Runtime (CLR). Considerare di nuovo l'esempio precedente. Se il resto dell'esempio rimane invariato e si modifica l'associazione <xref:System.Windows.Controls.TextBlock> a quanto riportato di seguito, i nomi degli XmlNode restituiti nell'<xref:System.Windows.Controls.ListBox>vengono visualizzati. In questo caso, il nome di tutti i nodi restituiti è "*Book*".  
  
 [!code-xaml[XmlDataSourceVariation#XmlNodePath](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSourceVariation/CS/Page1.xaml#xmlnodepath)]  
  
 In alcune applicazioni, l'incorporamento del codice XML come isola di dati all'interno dell'origine della pagina [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] può risultare scomodo perché il contenuto esatto dei dati deve essere noto in fase di compilazione. Per questo motivo, è supportato anche il recupero dei dati da un file XML esterno, come nell'esempio seguente:  
  
 [!code-xaml[XMLDataSource2#XmlFileExample](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlDataSource2/CS/Window1.xaml#xmlfileexample)]  
  
 Se i dati XML si trovano in un file XML remoto, è necessario definire l'accesso ai dati assegnando un URL appropriato all'attributo <xref:System.Windows.Data.XmlDataProvider.Source%2A> come indicato di seguito:  
  
```xml  
<XmlDataProvider x:Key="BookData" Source="http://MyUrl" XPath="Books"/>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.ObjectDataProvider>
- [Eseguire l'associazione ai risultati di una query XDocument, XElement o LINQ for XML](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)
- [Usare il modello Master-Details con dati XML gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [Panoramica delle origini di associazione](binding-sources-overview.md)
- [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
