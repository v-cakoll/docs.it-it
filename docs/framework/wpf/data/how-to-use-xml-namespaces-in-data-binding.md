---
title: "Procedura: utilizzare gli spazi dei nomi XML nell'associazione dati"
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- data binding [WPF], XML namespaces
- namespaces [WPF], XML
ms.assetid: a47c832f-dc84-48f2-96d5-cde18fc4284b
ms.openlocfilehash: f6e6e042fa5583fcf91bd15c524537490fb6670c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740582"
---
# <a name="how-to-use-xml-namespaces-in-data-binding"></a>Procedura: utilizzare gli spazi dei nomi XML nell'associazione dati
## <a name="example"></a>Esempio
 In questo esempio viene illustrato come gestire gli spazi dei nomi specificati nell'origine del binding XML.

 Se i dati XML hanno la definizione dello spazio dei nomi XML seguente:

 `<rss version="2.0" xmlns:dc="http://purl.org/dc/elements/1.1/">`

 È possibile usare l'elemento <xref:System.Windows.Data.XmlNamespaceMapping> per eseguire il mapping dello spazio dei nomi a una <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A>, come nell'esempio seguente. È quindi possibile utilizzare il <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> per fare riferimento allo spazio dei nomi XML. Il <xref:System.Windows.Controls.ListBox> in questo esempio Visualizza il *titolo* e il controller di dominio *: data* di ogni *elemento*.

 [!code-xaml[XmlnsBindSnippet#XmlNamespaceMapping](~/samples/snippets/csharp/VS_Snippets_Wpf/XmlnsBindSnippet/CS/Window1.xaml#xmlnamespacemapping)]

 Si noti che la <xref:System.Windows.Data.XmlNamespaceMapping.Prefix%2A> specificata non deve corrispondere a quella utilizzata nell'origine XML. Se il prefisso viene modificato nell'origine XML, il mapping continua a funzionare.

 In questo particolare esempio, i dati XML provengono da un servizio Web, ma l'elemento <xref:System.Windows.Data.XmlNamespaceMapping> funziona anche con dati XML o XML inline in un file incorporato.

## <a name="see-also"></a>Vedere anche

- [Eseguire l'associazione ai dati XML usando un oggetto XMLDataProvider e le query XPath](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
